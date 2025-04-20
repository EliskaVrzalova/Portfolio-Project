<script>
  import { fade, scale } from 'svelte/transition';
  import { quintOut } from 'svelte/easing';


  // Props
  export let src = '';
  export let poster = '';
  export let alt = '';
  export let description = '';
  
  // State
  let expanded = false;
  let videoElement;
  
  // Toggle expanded state
  function toggleExpand() {
    expanded = !expanded;
    
    // If closing the expanded view, we want to enable body scrolling again
    if (!expanded) {
      document.body.style.overflow = 'auto';
    } else {
      // Disable body scrolling when video is expanded
      document.body.style.overflow = 'hidden';
    }
  }
  
  // Close expanded view when clicking on overlay
  function handleOverlayClick(event) {
    // Only close if clicking directly on the overlay, not the content
    if (event.target === event.currentTarget) {
      toggleExpand();
    }
  }
  
  // Close on escape key
  function handleKeydown(event) {
    if (event.key === 'Escape' && expanded) {
      toggleExpand();
    }
  }
</script>

<svelte:window on:keydown={handleKeydown}/>

<div class="video-container">
  <!-- Video in gallery view -->
  <div 
    class="video-thumbnail"
    class:expanded={expanded}
    on:click={toggleExpand}
    role="button"
    tabindex="0"
  >
    <video 
      src={src}
      poster={poster}
      muted
      loop
      autoplay
      playsinline
      preload="metadata"
      class="video-element"
    >
      {alt}
    </video>
    <div class="click-indicator">
      <span>Click to view</span>
    </div>
  </div>
  
  <!-- Expanded overlay -->
  {#if expanded}
    <div 
      class="overlay" 
      on:click={handleOverlayClick}
      transition:fade={{ duration: 300 }}
    >
      <div 
        class="expanded-content"
        transition:scale={{ 
          duration: 400, 
          delay: 100,
          opacity: 1,
          start: 0.8, 
          easing: quintOut 
        }}
      >
        <video 
          src={src} 
          controls
          autoplay
          loop
          bind:this={videoElement}
          class="expanded-video"
        >
          {alt}
        </video>
        {#if description}
          <div class="description" transition:fade={{ delay: 300, duration: 300 }}>
            <p>{description}</p>
          </div>
        {/if}
      </div>
    </div>
  {/if}
</div>

<style>
  .video-container {
    position: relative;
    width: 100%;
    margin-bottom: 20px;
  }
  
  .video-thumbnail {
    cursor: pointer;
    transition: transform 0.3s ease, opacity 0.3s ease;
    position: relative;
    overflow: hidden;
    border-radius: 5px;
    background-color: #000;
  }
  
  .video-element {
    width: 100%;
    height: auto;
    display: block;
    border-radius: 5px;
    transition: transform 0.5s ease, opacity 0.5s ease;
    background-color: var(--primary-color);
    box-shadow: 0 3px 10px rgba(0, 0, 0, 0.2);
  }
  
  .click-indicator {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) scale(0.8);
    background-color: rgba(84, 21, 123, 0.7);
    color: white;
    padding: 10px 15px;
    border-radius: 25px;
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: 0;
    transition: opacity 0.3s ease, transform 0.3s ease;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
    pointer-events: none;
    font-size: 0.9rem;
    font-weight: 500;
  }
  
  .video-thumbnail:hover .click-indicator {
    opacity: 1;
    transform: translate(-50%, -50%) scale(1);
  }

  /* Expanded video overlay */
  .overlay {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.85);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 1000;
    padding: 20px;
    overflow: auto;
    backdrop-filter: blur(3px);
  }
  
  .expanded-content {
    max-width: 90vw;
    max-height: 90vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    position: relative;
  }
  
  .expanded-video {
    max-width: 100%;
    max-height: 80vh;
    object-fit: contain;
    border-radius: 5px;
    box-shadow: 0 5px 30px rgba(0, 0, 0, 0.3);
  }
  
  .description {
    background-color: rgba(84, 21, 123, 0.7);
    color: white;
    padding: 15px 20px;
    border-radius: 8px;
    margin-top: 15px;
    max-width: 600px;
    width: 100%;
    text-align: center;
  }
  
  .description p {
    margin: 0;
    font-size: 1.1rem;
    line-height: 1.5;
  }
  
  /* Gallery hover effect */
  :global(.gallery:hover) .video-thumbnail .video-element {
    opacity: 0.7;
  }
  
  :global(.gallery) .video-thumbnail:hover .video-element {
    transform: scale(1.05);
    opacity: 1;
  }
</style>


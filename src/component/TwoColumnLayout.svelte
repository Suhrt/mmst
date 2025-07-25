<!-- TwoColumnLayout.svelte -->
<script>
  // Optional props for customization
  export let containerClass = "container mx-auto px-4 py-8 max-w-6xl";
  export let gridClass = "grid grid-cols-1 lg:grid-cols-2 gap-6";
  export let leftColumnClass = "space-y-6";
  export let rightColumnClass = "space-y-6";
  export let breakpoint = "lg"; // sm, md, lg, xl, 2xl
</script>

<div class={containerClass}>
  <div class={gridClass.replace('lg', breakpoint)}>
    
    <!-- Left Column Slot -->
    <div class={leftColumnClass}>
      <slot name="left">
        <!-- Default content if no left slot provided -->
        <div class="bg-white rounded-lg border border-gray-200 shadow-sm p-6">
          <h3 class="text-lg font-semibold text-gray-900 mb-2">Left Column</h3>
          <p class="text-gray-600">Add content using slot="left"</p>
        </div>
      </slot>
    </div>

    <!-- Right Column Slot -->
    <div class={rightColumnClass}>
      <slot name="right">
        <!-- Default content if no right slot provided -->
        <div class="bg-white rounded-lg border border-gray-200 shadow-sm p-6">
          <h3 class="text-lg font-semibold text-gray-900 mb-2">Right Column</h3>
          <p class="text-gray-600">Add content using slot="right"</p>
        </div>
      </slot>
    </div>
    
  </div>
</div>

<!-- 
Usage Example:

<TwoColumnLayout>
  <div slot="left">
    <h2>Main Content</h2>
    <p>Your main content goes here...</p>
  </div>
  
  <div slot="right">
    <h2>Sidebar</h2>
    <p>Your sidebar content goes here...</p>
  </div>
</TwoColumnLayout>

Custom breakpoint:
<TwoColumnLayout breakpoint="md">
  // content
</TwoColumnLayout>

Custom classes:
<TwoColumnLayout 
  containerClass="max-w-4xl mx-auto px-6"
  gridClass="grid grid-cols-1 md:grid-cols-3 gap-8"
>
  // content
</TwoColumnLayout>
-->
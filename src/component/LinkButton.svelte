<!-- LinkButton.svelte -->
<script>
    export let href = "#";
    export let text = "Click here";
    export let external = false;
    export let textSize = "text-base";
</script>

<a
    {href}
    class="group inline-flex items-center justify-between w-full transition-colors duration-200 hover:text-[#FFEBCD] {textSize} py-4"
    target={external ? "_blank" : undefined}
    rel={external ? "noopener noreferrer" : undefined}
>
    <div class="group-hover:underline decoration-dotted underline-offset-4">{text}</div>
    <div class="transition-transform duration-1000 group-hover:-translate-x-10">→</div>
</a>
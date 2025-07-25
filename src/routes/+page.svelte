<script>
    import TwoColumnLayout from "../component/TwoColumnLayout.svelte";

    import Links from "./Links.svelte";

    let showCaption = $state(false);
</script>

<div class="w-full md:h-screen bg-red-800 text-white">
    <TwoColumnLayout>
        <div slot="left" class="flex flex-col justify-center items-start">
            <div>
                <p class="text-lg">We are</p>
                <h1
                    class="text-5xl md:text-7xl font-bold mt-0 leading-none mb-2"
                >
                    <span class="relative">
                        <span class="text-[#FFEBCD]">M</span>asters<br />
                        of <span class="text-[#FFEBCD]">M</span>edical<br />
                        <span class="text-[#FFEBCD]">S</span>cience<br />
                        &amp; <span class="text-[#FFEBCD]">T</span>echnology
                    </span>
                </h1>
                <p class="text-lg mb-4 md:mb-8">@ IIT Kharagpur</p>
            </div>
            <div class="hidden md:block">
            <Links/>
            </div>
        </div>

        <div
            slot="right"
            class="flex flex-col justify-center items-center h-full"
        >
            <div class="relative">
                <img
                    src="/mmst_24.jpeg"
                    alt="2024 Batch of MMST, taken during cad classes"
                    class="w-full aspect-square object-cover border-4 border-white"
                />

                <div class="flex flex-row w-full absolute bottom-0 left-0">
                    <button
                        onclick={() => {showCaption = !showCaption;}}
                        class="group z-10 bg-white p-2 hover:bg-transparent text-yellow-500 h-10 w-10 cursor-pointer duration-1000 "
                        aria-label="Toggle image caption"
                    >
                        <span class="opacity-100">&#10059;</span>
                    </button>

                    {#if showCaption}
                        <div
                            class="bg-white text-black p-1 w-full"
                        >
                            Doctors in CAD classes - MMST 2024 Batch
                        </div>
                    {/if}
                </div>
            </div>
            <div class="mt-4 block md:hidden">
            <Links/>
            </div>
        </div>
    </TwoColumnLayout>
</div>
<div><h1>Built using svelte 5 & deployed via cloudflare pages</h1></div>

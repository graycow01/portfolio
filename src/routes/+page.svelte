<script>
      import donut from "$lib/assets/donut.png";

      import { FontAwesomeIcon } from "@fortawesome/svelte-fontawesome";
      import { faDiscord, faGithub } from "@fortawesome/free-brands-svg-icons";
      import { config } from "@fortawesome/fontawesome-svg-core";

      import "@fortawesome/fontawesome-svg-core/styles.css";
      config.autoAddCss = false;

      import { createPopperActions } from 'svelte-popperjs';
        const [popperRef, popperContent] = createPopperActions({
            placement: 'right',
            strategy: 'fixed',
        });
        const extraOpts = {
            modifiers: [
            { name: 'offset', options: { offset: [12, 12] } }
            ],
        };

        let showTooltip = false;

</script>

<svelte:head>
      <title>graycow01's site</title>
</svelte:head>

<div
      class="w-full h-full flex flex-col items-center px-6 pt-16 pb-4 2xl:w-2/5 lg:w-1/2 md:w-3/5 sm:w-2/3"
>
      <img src={donut} alt="Donut" class="pb-8 w-60 h-60" />
      <h1 class="font-semibold text-3xl mb-2">graycow01</h1>
      <p class="text-gray-200 text-sm mb-2">
            TJHSST Class of 2028 • Fairfax, VA
      </p>
      <div class="mb-6 flex flex-row gap-4">
            <a href="https://github.com/graycow01" target="_blank" class=""
                  ><FontAwesomeIcon
                        icon={faGithub}
                        class="fa-xl hover:text-blue-500"
                  /></a
            >
            <div
            use:popperRef
            role="button"
            tabindex="0"
            on:mouseenter={() => showTooltip = true}
            on:mouseleave={() => showTooltip = false}>
                <FontAwesomeIcon
                icon={faDiscord}
                class="fa-xl hover:text-blue-500"
                />
            </div>
            

            {#if showTooltip}
                <div id="tooltip" use:popperContent={extraOpts} class="text-sm bg-gray-900 p-2 rounded-md">
                    graycow
                    <div id="arrow" data-popper-arrow />
                </div>
            {/if}
      </div>
      <p class="text-sm text-center sm:text-left mb-8">
            Hey! I'm a high school programmer always learning new things. I spend most my time competitive programming and doing CTFs, but I enjoy doing web development.
      </p>
      <div class="flex flex-col items-start w-full mb-2">
            <p class="text-gray-200 text-left text-xs mb-2">Things I Know/Use</p>
            <div class="flex flex-wrap gap-2 text-green-600 text-xs">
                  <div class="bg-green-950 rounded-full p-1 px-2">python</div>
                  <div class="bg-green-950 rounded-full p-1 px-2">c++</div>
                  <div class="bg-green-950 rounded-full p-1 px-2">java</div>
                  <div class="bg-green-950 rounded-full p-1 px-2">nodejs</div>
                  <div class="bg-green-950 rounded-full p-1 px-2">svelte</div>
                  <div class="bg-green-950 rounded-full p-1 px-2">
                        tailwindcss
                  </div>
                  <div class="bg-green-950 rounded-full p-1 px-2">vscode</div>
                  <div class="bg-green-950 rounded-full p-1 px-2">
                        wsl
                  </div>
                  <div class="bg-green-950 rounded-full p-1 px-2">git</div>
            </div>
      </div>
      <div class="flex flex-col items-start w-full">
            <p class="text-gray-200 text-left text-xs mb-2">
                  Things I'm Learning
            </p>
            <div class="flex flex-wrap gap-2 text-orange-600 text-xs">
                  <div class="bg-orange-950 rounded-full p-1 px-2">binary search</div>
                  <div class="bg-orange-950 rounded-full p-1 px-2">sorting</div>
                  <div class="bg-orange-950 rounded-full p-1 px-2">recursion</div>
            </div>
      </div>
      <div class="grow flex flex-col justify-end">
            <p class="text-gray-500 text-xs">Last updated 11/02/2024</p>
      </div>
</div>

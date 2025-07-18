<script lang="ts">
  import { stat } from "../../store";
  import { animateValue } from "../../utils";
  import Skeleton from "../../misc/Skeleton.svelte";

  let objValue: any;

  $: if (!stat.loading) {
    stat.balanceCoins.then(value => {
      objValue = value;
    });
  }
</script>

<div class="flex flex-col gap-2 items-center mb-6 md:mb-10">
  <h3 class="text-[#ffffffb9] uppercase text-xs md:text-base">total balance</h3>
  <div class="flex gap-2 md:gap-4 items-center justify-center">
    <img
      class="w-10 h-10 md:w-[4.5rem] md:h-[4.5rem]"
      src="/images/tcg_coin_512x512.png"
      alt="TCG Coin"
      draggable="false"
    />
    <div
      class="font-extrabold lining-nums tabular-nums text-2xl sm:text-3xl md:text-5xl lg:text-6xl"
      bind:this={objValue}
    >
      {#if stat.loading}
        <Skeleton className="w-44 h-7 sm:w-72 sm:h-10 md:w-96 md:h-14 md:rounded-lg lg:w-[32rem] lg:h-16 lg:rounded-xl" />
      {:else if objValue !== undefined}
        {@html animateValue(objValue, objValue)}
      {/if}
    </div>
  </div>
</div>

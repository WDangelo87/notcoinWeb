<script lang="ts">
  import { onMount } from 'svelte';
  import { getTotalBalance } from '../../utils';
  import { playerCount, onlineToday, onlineNow } from '../../store';

  let totalBalance: number = 0;

  onMount(async () => {
    totalBalance = await getTotalBalance();
  });
</script>

<div class="balance">
  <h1 class="title">
    <img src="/coin.png" alt="Coin" width="48" height="48" />
    <span>{totalBalance}</span>
  </h1>

  <ul class="stats">
    <li>
      <span class="dot" /> {playerCount} <span>total players</span>
    </li>
    <li>
      <span class="dot" /> {onlineToday} <span>online today</span>
    </li>
    <li>
      <span class="dot" /> {onlineNow} <span>online</span>
    </li>
  </ul>
</div>

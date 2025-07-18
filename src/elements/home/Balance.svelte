<script lang="ts">
  import { onMount } from 'svelte';
  import { getTotalBalance } from '../../utils';
  import { playerCount, onlineToday, onlineNow } from '../../store';
  import Coin from '../misc/Skeleton.svelte'; // ✅ This path is now correct relative to "home/"

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
      <Coin /> {playerCount} <span>total players</span>
    </li>
    <li>
      <Coin /> {onlineToday} <span>online today</span>
    </li>
    <li>
      <Coin /> {onlineNow} <span>online</span>
    </li>
  </ul>
</div>

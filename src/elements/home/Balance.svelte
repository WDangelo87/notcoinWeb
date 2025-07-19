<script lang="ts">
  let totalBalance = 0;
</script>

<div class="balance">
  <h1 class="title">
    <img src="/images/tcg_coin_512x512.png" alt="Coin" class="coin-icon" />
    <span>{totalBalance}</span>
  </h1>

  <ul class="stats">
    <li>
      <span class="dot" /> <span>total players</span>
    </li>
    <li>
      <span class="dot" /> <span>online today</span>
    </li>
    <li>
      <span class="dot" /> <span>online</span>
    </li>
  </ul>
</div>

<style>
  .coin-icon {
    width: 32px;
    height: 32px;
    margin-right: 8px;
    vertical-align: middle;
  }
</style>

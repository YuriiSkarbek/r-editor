<template>
  <div class="toolkit">
    <div class="toolkit-group">
      <button class="toolkit-item">
        <img src="@/assets/icons/bold.svg" alt="Bold">
      </button>
      <button class="toolkit-item">
        <img src="@/assets/icons/italic.svg" alt="italic">
      </button>
      <button class="toolkit-item">
        <img src="@/assets/icons/underline.svg" alt="underline">
      </button>
      <button class="toolkit-item">
        <img src="@/assets/icons/strike.svg" alt="strike">
      </button>
    </div>
    <div class="toolkit-group">
      <div class="toolkit-item">
        Size:
      </div>
      <select>
        <option value="10">10</option>
        <option value="12">12</option>
        <option value="14">14</option>
        <option value="16">16</option>
        <option value="20">20</option>
        <option value="24">24</option>
        <option value="32">32</option>
      </select>
    </div>
    <div class="toolkit-group">
      <div class="toolkit-item">
        Color:
      </div>
      <input type="color">
    </div>
    <div class="toolkit-group">
      <div class="toolkit-item">
        Background:
      </div>
      <input type="color" value="#fff">
    </div>
  </div>
</template>

<style>
  .toolkit {
    width: 100%;
    height: auto;
    display: flex;
    padding: 0 4px 4px 4px;
  }

  .toolkit-group {
    display: flex;
    border-right: 1px solid #ccc;
  }

  .toolkit-group select {
    display: block;
    width: 40px;
    border: none;
    outline: none;
    margin-right: 8px;
  }

  .toolkit-group input[type=color] {
    width: 20px;
    margin-right: 8px;
  }

  .toolkit-item {
    padding: 4px 8px;
    background-color: transparent;
    border: none;
    outline: none;
    opacity: .7;
    transition: .4s;
    cursor: pointer;
  }

  .toolkit-item:hover {
    opacity: 1;
  }

  .toolkit-item img {
    width: auto;
    height: 16px;
  }
</style>
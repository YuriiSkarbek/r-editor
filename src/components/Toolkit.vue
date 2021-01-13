<template>
  <div class="toolkit">
    <div class="toolkit-group">
      <button class="toolkit-item" @click="$emit('style-text', 'bold')">
        <img src="@/assets/icons/bold.svg" alt="Bold">
      </button>
      <button class="toolkit-item" @click="$emit('style-text', 'italic')">
        <img src="@/assets/icons/italic.svg" alt="italic">
      </button>
      <button class="toolkit-item" @click="$emit('style-text', 'underline')">
        <img src="@/assets/icons/underline.svg" alt="underline">
      </button>
      <button class="toolkit-item" @click="$emit('style-text', 'strikethrough')">
        <img src="@/assets/icons/strike.svg" alt="strike">
      </button>
    </div>
    <label class="toolkit-group">
      <div class="toolkit-item">
        Size:
      </div>
      <select @change="$emit('style-text', 'fontSize', $event.target.value)">
        <option value="1">Small</option>
        <option value="3">Normal</option>
        <option value="5">Large</option>
        <option value="7">X-Large</option>
      </select>
    </label>
    <label class="toolkit-group">
      <div class="toolkit-item">
        Color:
      </div>
      <input type="color" @change="$emit('style-text', 'foreColor', $event.target.value)">
    </label>
    <label class="toolkit-group">
      <div class="toolkit-item">
        Background:
      </div>
      <input type="color" value="#fff" @change="$emit('style-text', 'hiliteColor', $event.target.value)">
    </label>
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
    font-family: Helvetica, sans-serif;
    display: block;
    width: 70px;
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
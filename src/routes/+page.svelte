<script lang="ts">
  import { createEventDispatcher } from "svelte";
  import Input from "../components/Input.svelte";
  import image from "$lib/assets/mail.png";

  let inputValue = "";
  let placeholder = "Enter Email...";
  // let hint = 'This is a hint.';
  let error = "Not an Email..";
  let addonLeft = image;
  let addonRight = image;
  let addonAlt = "&";

  const dispatch = createEventDispatcher();

  $: console.log(inputValue);
</script>

<div class="flex justify-center items-center h-screen">
  <Input
    labelName={"Email"}
    {addonLeft}
    {addonRight}
    {addonAlt}
    bind:value={inputValue}
    {placeholder}
    hint={"Hint : Enter a valid email address"}
    {error}
    on:input={(e) => console.log(e.detail)}
    roundedStyle="rounded-lg"
  />
</div>

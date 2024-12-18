<script>

  let level = $props();
  const colors = [
      '#e7efc5',
      '#ead8bb',
      '#edc0b1',
      '#efa9a7',
      '#f2919d',
      '#f57a93',
      '#f76289',
      '#fa4b7f',
      '#fd3375',
      '#ff1c6b'
  ];


  const fruityScale = {
0: {
  label: "Bro.",
  meaning: "Zero zest. Straight facts only."
},
1: {
  label: "ight bet",
  meaning: "Mildly invested, but still pretending it’s casual."
},
2: {
  label: "👀",
  meaning: "Suspiciously fruity. Something’s brewing."
},
3: {
  label: "lmfao ur wild",
  meaning: "Deflecting with humor but kinda into it."
},
4: {
  label: "ANYWAY 😐",
  meaning: "Desperately avoiding the fruity implications."
},
5: {
  label: "boy what 😭",
  meaning: "Shocked but intrigued; not as straight as advertised."
},
6: {
  label: "pls💅",
  meaning: "Sass fully unlocked, no turning back."
},
7: {
  label: "omg slayyyy",
  meaning: "Boldly flamboyant, living the fantasy."
},
8: {
  label: "YAAAS QUEEN",
  meaning: "Peak zest, throwing glitter in the chat."
},
9: {
  label: "✨🏳️‍🌈 gay. 🏳️‍🌈✨",
  meaning: "Yup ur gay."
}
};
  level = level["level"]
  let color = colors[level];
</script>


<div title="{fruityScale[level]["meaning"]}" style="order: {level};">
  <div style="background-color: {color}" class="color">
    <p>- {level+1}0% -</p>
  </div>
  <label for=""> - {fruityScale[level]["label"]}</label>
</div>

<style>
  /*https://coolors.co/413c58-a3c4bc-bfd7b5-e7efc5-f2e7c9*/
  
  .color {
      width: 5em;
      height: 2em;
  }
  div {
      display: flex;
      gap: 1em;
      align-items: center;
  }


  p {
    width: 100%;
    text-align: center;
    font-size: small;
  }
  
</style>
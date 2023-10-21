<script>
  import { T, useFrame } from "@threlte/core";

  let sticks = [];

  export let posY = 1;
  export let amount = 20;

  for (let i = 1; i <= amount; i++) {
    sticks.push(i);
  }

  let change = 0;

  useFrame((_, delta) => {
    change += delta;
  });
</script>

{#each sticks as stick}
  <T.Mesh
    position={[(6 / amount) * stick - 3.5, posY, 0]}
    rotation.x={stick * change * 0.1}
  >
    <T.BoxGeometry args={[0.1, stick * 0.1, 0.1]} />
    <T.MeshStandardMaterial
      color={`hsl(${(360 / amount) * stick}, 100%, 50%)`}
    />
  </T.Mesh>
{/each}

<script>
  import { T } from "@threlte/core";
  import { OrbitControls } from "@threlte/extras";

  import Sticks from "./Sticks.svelte";
</script>

<T.PerspectiveCamera makeDefault position={[0, 0, 20]} fov={30}>
  <OrbitControls enableDamping autoRotate autoRotateSpeed={0.1} />
</T.PerspectiveCamera>

<T.AmbientLight intensity={0.5} />
<T.DirectionalLight intensity={0.8} position.x={10} position.y={10} />

<Sticks amount={40} posY={-3} />
<Sticks />
<Sticks amount={10} posY={3.5} />

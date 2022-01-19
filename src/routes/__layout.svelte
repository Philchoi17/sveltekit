<script lang="ts">
  import Header from '$lib/Components/Header/Header.svelte'
  import Footer from '$lib/Components/Footer/Footer.svelte'
  import { Container, Button, Offcanvas, Row, Col } from 'sveltestrap'
  import '../app.css'

  let openLeft = false
  let openRight = false

  const toggleLeft = () => (openLeft = !openLeft)
  const toggleRight = () => (openRight = !openRight)
</script>

<Header />

<Offcanvas
  isOpen={openLeft}
  toggle={toggleLeft}
  header="Start"
  placement="start"
>
  Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
  tempor incididunt ut labore et dolore magna aliqua.
</Offcanvas>

<Offcanvas
  isOpen={openRight}
  toggle={toggleRight}
  placement="end"
  header="Right"
>
  Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
  tempor incididunt ut labore et dolore magna aliqua.
</Offcanvas>

<Button size="sm" on:click={toggleLeft} />

<main>
  <Container>
    <slot />
  </Container>
</main>
<Button size="sm" on:click={toggleRight} />

<Footer />

<style>
  main {
    flex: 1;
    display: flex;
    flex-direction: column;
    padding: 1rem;
    width: 100%;
    max-width: 1024px;
    margin: 0 auto;
    box-sizing: border-box;
  }

  /* .offcanvas-left-right-buttons-container {
    justify-content: fle;
    align-items: stretch;
    position: absolute;
    top: 50%;
  }

  .offcanvas-left-right-buttons {
    border: 1px solid black;
  } */
</style>

<script lang="ts">
  import { Nav, NavLink, Container, Button, Offcanvas } from 'sveltestrap'
  let open = false
  const toggle = () => (open = !open)
</script>

<footer>
  <Container>
    <p>built by <a href="#">me</a></p>
    <Button on:click={toggle} />
    <Nav>
      <NavLink href="#">Link</NavLink>
      <NavLink href="#">Link</NavLink>
      <NavLink href="#">Another Link</NavLink>
      <NavLink disabled href="#">Disabled Link</NavLink>
    </Nav>
  </Container>
</footer>

<Offcanvas isOpen={open} {toggle} placement="bottom" header="Right">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
  tempor incididunt ut labore et dolore magna aliqua.
</Offcanvas>

<style>
  footer {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 40px;
  }

  footer a {
    font-weight: bold;
  }

  @media (min-width: 480px) {
    footer {
      padding: 40px 0;
    }
  }
</style>

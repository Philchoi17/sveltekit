<script lang="ts">
  import {
    Collapse,
    Navbar,
    NavbarToggler,
    NavbarBrand,
    Nav,
    NavItem,
    NavLink,
    Dropdown,
    DropdownToggle,
    DropdownMenu,
    DropdownItem,
    Offcanvas,
    Button,
  } from 'sveltestrap'

  let isOpen = false
  let open = false
  const toggle = () => (open = !open)
  function handleUpdate(event) {
    isOpen = event.detail.isOpen
  }
</script>

<Offcanvas isOpen={open} {toggle} header="Start" placement="top">
  <div>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
    tempor incididunt ut labore et dolore magna aliqua.
  </div>
  <Button on:click={toggle}>Close</Button>
</Offcanvas>
<Navbar color="light" light expand="md">
  <NavbarBrand href="/">BURNER</NavbarBrand>
  <NavbarToggler on:click={() => (isOpen = !isOpen)} />
  <Button on:click={toggle} />
  <Collapse {isOpen} navbar expand="md" on:update={handleUpdate}>
    <Nav class="ms-auto" navbar>
      <NavItem>
        <NavLink href="/about">About</NavLink>
      </NavItem>
      <NavItem>
        <NavLink href="https://github.com/bestguy/sveltestrap">GitHub</NavLink>
      </NavItem>
      <Dropdown nav inNavbar>
        <DropdownToggle nav caret>Options</DropdownToggle>
        <DropdownMenu end>
          <DropdownItem>Option 1</DropdownItem>
          <DropdownItem>Option 2</DropdownItem>
          <DropdownItem divider />
          <DropdownItem>Reset</DropdownItem>
        </DropdownMenu>
      </Dropdown>
    </Nav>
  </Collapse>
</Navbar>

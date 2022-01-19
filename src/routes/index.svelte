<script module="module" lang="ts">
  import { Row, Col, Button, Image } from 'sveltestrap'
  import Card from '$lib/Components/Card/Card.svelte'

  export const prerender = true

  import Carousel from '$lib/Components/Carousel/Carousel.svelte'
  import Tabs from '$lib/Components/Tabs/Tabs.svelte'
  let state = {
    textBoxes: [
      {
        header: 'Header1',
        subTitle: 'SubTitle1',
        body: 'BODYTEXTBODYTEXT',
        buttonText: 'press',
        footer: 'FOOTER',
      },
      {
        header: 'Header2',
        subTitle: 'SubTitle2',
        body: 'BODYTEXTBODYTEXT',
        buttonText: 'press',
        footer: 'FOOTER',
      },
      {
        header: 'Header3',
        subTitle: 'SubTitle3',
        body: 'BODYTEXTBODYTEXT',
        buttonText: 'press',
        footer: 'FOOTER',
      },
    ],
  }

  const pictures: string[] = [
    'https://picsum.photos/id/426/600/400.jpg',
    'https://picsum.photos/id/427/600/400.jpg',
    'https://picsum.photos/id/428/600/400.jpg',
    'https://picsum.photos/id/429/600/400.jpg',
    'https://picsum.photos/id/430/600/400.jpg',
    'https://picsum.photos/id/431/600/400.jpg',
    'https://picsum.photos/id/432/600/400.jpg',
    'https://picsum.photos/id/433/600/400.jpg',
    'https://picsum.photos/id/434/600/400.jpg',
    'https://picsum.photos/id/435/600/400.jpg',
    'https://picsum.photos/id/436/600/400.jpg',
    'https://picsum.photos/id/437/600/400.jpg',
  ]
</script>

<svelte:head>
  <title>Home</title>
</svelte:head>

<section>
  <Carousel items={pictures} />
  <Tabs />
</section>
<Row>
  {#each state.textBoxes as textBox}
    <Col>
      <Card {...textBox} />
    </Col>
  {/each}
</Row>

<style>
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex: 1;
  }

  h1 {
    width: 100%;
  }

  .welcome {
    position: relative;
    width: 100%;
    height: 0;
    padding: 0 0 calc(100% * 495 / 2048) 0;
  }

  .welcome img {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    display: block;
  }
</style>

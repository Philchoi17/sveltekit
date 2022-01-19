<script lang="ts">
  import {
    Button,
    Card,
    CardBody,
    CardFooter,
    CardHeader,
    CardSubtitle,
    CardText,
    CardTitle,
  } from 'sveltestrap'

  export let header: string
  export let subTitle: string
  export let body: string
  export let buttonText: string
  export let footer: string
</script>

<Card class="mb-3">
  <CardHeader>
    <CardTitle>{header}</CardTitle>
  </CardHeader>
  <CardBody>
    <CardSubtitle>{subTitle}</CardSubtitle>
    <CardText>
      {body}
    </CardText>
    <Button>{buttonText}</Button>
  </CardBody>
  <CardFooter>{footer}</CardFooter>
</Card>

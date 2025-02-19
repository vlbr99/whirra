<script>
  import Accordion from "./Accordion.svelte";

  const accordionItems = [
    { title: "Section 1", content: "Content for section 1" },
    { title: "Section 2", content: "Content for section 2" },
    { title: "Section 3", content: "Content for section 3" },
  ];
</script>

<Accordion items={accordionItems} />

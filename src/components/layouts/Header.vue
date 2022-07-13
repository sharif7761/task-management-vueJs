<template>
    <header>
        {{title}}
    </header>
</template>

<script>
export default {
    name: "HeaderComp",
    props: {
        title: String
    }
}
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>

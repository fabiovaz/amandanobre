<template>
  <div>
    <aside>
      <div class="profile">
        imagem
      </div>
      <nav>
        <a href="/about">About</a>
        <a href="/about">Works</a>
      </nav>
    </aside>
    <main>
      <Nuxt />
    </main>
  </div>
</template>

<script>
export default {}
</script>

<style>
aside {
  position: fixed;
  width: 360px;
  background: red;
  height: 100%;
}
main {
  padding: 0 15px;
  margin-left: 360px;
}
</style>

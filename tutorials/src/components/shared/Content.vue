<template>
  <div>
    <div class="navigation">
      <ul>
        <li>
          <a href="#">C#</a>
        </li>
        <li>
          <a href="#">JAVASCRIPT</a>
        </li>
        <li>
          <a href="#">JAVA</a>
        </li>
        <li>
          <a href="#">PYTHON</a>
        </li>
      </ul>

      <ul>
        <li>
          <a href="#">SUBJECT [+]</a>
        </li>
      </ul>
    </div>
    <div class="main-content">
      <aside class="content-navigation">
          <slot name="nav"></slot>
        
      </aside>
      <section class="content-info">
          <slot name="info"></slot>
      </section>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped></style>

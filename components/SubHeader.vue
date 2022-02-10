<template>
  <div class="sub-header">
    <div class="sub-header-content container">
      <nav>
        <ul class="sub-header-nav">
          <li>
            <a href="#"> Overview </a>
          </li>
          <li>
            <a href="#"> Notifications </a>
          </li>
          <li>
            <a href="#"> Analytics </a>
          </li>
          <li>
            <a href="#"> Saved reports </a>
          </li>
          <li>
            <a href="#"> Trade history </a>
          </li>
          <li>
            <a href="#"> User reports </a>
          </li>
        </ul>
      </nav>

      <app-search />
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.sub-header {
  border-bottom: 1px solid #e3e8ee;

  @media (max-width: 768px) {
    display: none;
  }
}

.sub-header-content {
  display: flex;
  width: 100%;
  justify-content: space-between;
  align-items: center;
  height: 64px;
}

.sub-header-nav {
  display: flex;
  width: 100%;
  justify-content: space-between;
  align-items: center;
  gap: 16px;

  @media (max-width: 1024px) {
    gap: 5px;
  }

  @media (max-width: 768px) {
    display: none;
  }

  li {
    margin: 0 12px;

    @media (max-width: 1024px) {
      margin: 0 5px;
    }
  }

  a {
    color: rgba(52, 64, 84, 1);
    font-weight: 500;
    font-size: 16px;
  }
}
</style>
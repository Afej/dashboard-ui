<template>
  <div class="search-wrapper">
    <svg
      width="18"
      height="18"
      viewBox="0 0 18 18"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M16.5 16.5L12.875 12.875M14.8333 8.16667C14.8333 11.8486 11.8486 14.8333 8.16667 14.8333C4.48477 14.8333 1.5 11.8486 1.5 8.16667C1.5 4.48477 4.48477 1.5 8.16667 1.5C11.8486 1.5 14.8333 4.48477 14.8333 8.16667Z"
        stroke="#667085"
        stroke-width="1.66667"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </svg>

    <input type="search" class="search" placeholder="Search" />
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.search-wrapper {
  position: relative;
  display: flex;
  align-items: center;

  @media (max-width: 768px) {
    width: 100%;
  }
}

.search {
  width: 320px;
  height: 44px;
  background: #ffffff;
  border: 1px solid #d0d5dd;
  box-shadow: 0px 1px 2px rgba(16, 24, 40, 0.05);
  border-radius: 8px;
  outline: none;
  padding: 10px 40px;
  font-weight: normal;
  font-size: 16px;
  line-height: 24px;
  color: #667085;

  @media (max-width: 768px) {
    width: 100%;
  }
}

svg {
  position: absolute;
  left: 10px;
}
</style>
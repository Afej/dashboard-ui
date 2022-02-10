<template>
  <div class="filter-tag">
    {{ text }}
    <!-- times (x) icon -->
    <svg
      width="12"
      height="12"
      viewBox="0 0 12 12"
      fill="none"
      xmlns="http://www.w3.org/2000/svg"
    >
      <path
        d="M11 1L1 11M1 1L11 11"
        stroke="#6941C6"
        stroke-width="1.67"
        stroke-linecap="round"
        stroke-linejoin="round"
      />
    </svg>
  </div>
</template>

<script>
export default {
  props: {
    text: {
      required: true,
      type: String,
    },
  },
};
</script>

<style lang="scss" scoped>
.filter-tag {
  display: flex;
  align-items: center;
  padding: 10px 16px;
  background: #f9f5ff;
  border: 1px solid #f9f5ff;
  box-sizing: border-box;
  box-shadow: 0px 1px 2px rgba(16, 24, 40, 0.05);
  border-radius: 8px;
  font-weight: 500;
  font-size: 14px;
  gap: 13px;
  line-height: 20px;
  color: #6941c6;
  cursor: pointer;

  @media (max-width: 768px) {
    padding: 2px 8px 2px 10px;
    border-radius: 16px;
  }
}
</style>
<template>
  <table>
    <thead>
      <tr>
        <th class="dropdown-icon">
          <svg
            width="20"
            height="20"
            viewBox="0 0 20 20"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M0 6C0 2.68629 2.68629 0 6 0H14C17.3137 0 20 2.68629 20 6V14C20 17.3137 17.3137 20 14 20H6C2.68629 20 0 17.3137 0 14V6Z"
              fill="#F9F5FF"
            />
            <path
              d="M5.91669 10H14.0834"
              stroke="#7F56D9"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
            <path
              d="M6 1H14V-1H6V1ZM19 6V14H21V6H19ZM14 19H6V21H14V19ZM1 14V6H-1V14H1ZM6 19C3.23858 19 1 16.7614 1 14H-1C-1 17.866 2.13401 21 6 21V19ZM19 14C19 16.7614 16.7614 19 14 19V21C17.866 21 21 17.866 21 14H19ZM14 1C16.7614 1 19 3.23858 19 6H21C21 2.13401 17.866 -1 14 -1V1ZM6 -1C2.13401 -1 -1 2.13401 -1 6H1C1 3.23858 3.23858 1 6 1V-1Z"
              fill="#7F56D9"
            />
          </svg>
        </th>
        <th class="company">
          Company
          <svg
            width="12"
            height="12"
            viewBox="0 0 12 12"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M5.99998 1.33333V10.6667M5.99998 10.6667L10.6666 6M5.99998 10.6667L1.33331 6"
              stroke="#667085"
              stroke-width="1.33333"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </th>
        <th class="">License use</th>
        <th class="">Status</th>
        <th class="">Users</th>
        <th class="">About</th>
        <th class="icons"></th>
      </tr>
    </thead>
    <tbody :key="company.id" v-for="company in companies">
      <single-company :company="company" />
    </tbody>
  </table>
</template>

<script>
export default {
  name: "Companies",
  props: {
    companies: Array,
  },
};
</script>

<style lang="scss" scoped>
table {
  border-collapse: collapse;
  width: 100%;
}

th {
  padding: 12px 24px;
  // height: 44px;
  background: #ffffff;
  font-weight: 500;
  font-size: 12px;
  line-height: 18px;
  color: #667085;
  text-align: left;

  &.dropdown-icon {
    padding-right: 0;
  }
  &.company {
    padding-left: 0;
    left: 0;
    position: relative;
  }
}
</style>
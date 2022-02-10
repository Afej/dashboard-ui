<template>
  <div class="card">
    <div class="card-heading">
      <span>{{ data.name }}</span>

      <!-- dropdown icon -->
      <svg
        width="4"
        height="16"
        viewBox="0 0 4 16"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M2.33333 8.83334C2.79357 8.83334 3.16667 8.46025 3.16667 8.00001C3.16667 7.53977 2.79357 7.16668 2.33333 7.16668C1.8731 7.16668 1.5 7.53977 1.5 8.00001C1.5 8.46025 1.8731 8.83334 2.33333 8.83334Z"
          stroke="#98A2B3"
          stroke-width="1.66667"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
        <path
          d="M2.33333 3.00001C2.79357 3.00001 3.16667 2.62691 3.16667 2.16668C3.16667 1.70644 2.79357 1.33334 2.33333 1.33334C1.8731 1.33334 1.5 1.70644 1.5 2.16668C1.5 2.62691 1.8731 3.00001 2.33333 3.00001Z"
          stroke="#98A2B3"
          stroke-width="1.66667"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
        <path
          d="M2.33333 14.6667C2.79357 14.6667 3.16667 14.2936 3.16667 13.8333C3.16667 13.3731 2.79357 13 2.33333 13C1.8731 13 1.5 13.3731 1.5 13.8333C1.5 14.2936 1.8731 14.6667 2.33333 14.6667Z"
          stroke="#98A2B3"
          stroke-width="1.66667"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
      </svg>
    </div>

    <div class="card-info">
      <div class="numbers">
        <h4>{{ data.number }}</h4>

        <p>
          <span>
            <!-- percentage inc/dec -->
            <svg
              width="14"
              height="14"
              viewBox="0 0 14 14"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
              v-if="data.positive"
            >
              <path
                d="M7.00002 12.8333V1.16666M7.00002 1.16666L1.16669 6.99999M7.00002 1.16666L12.8334 6.99999"
                stroke="#12B76A"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>

            <!-- percentage inc/dec -->
            <svg
              width="15"
              height="14"
              viewBox="0 0 15 14"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
              v-else
            >
              <path
                d="M7.33333 1.16666V12.8333M7.33333 12.8333L13.1667 6.99999M7.33333 12.8333L1.5 6.99999"
                stroke="#F04438"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>

            {{ data.percent }}%
          </span>
          vs last month
        </p>
      </div>
      <div class="chart">
        <!-- render svg based on card info -->
        <svg
          width="131"
          height="66"
          viewBox="0 0 131 66"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
          v-if="data.positive"
        >
          <path
            d="M129.333 1C108.537 2.73299 107.25 44.2218 86.6667 49C69.6936 52.9402 61.0989 30.5738 44 33C25.4537 35.6316 19.5189 58.9382 1.33337 65H129.333V1Z"
            fill="#ECFDF3"
          />
          <path
            d="M129.333 1C108.537 2.73299 107.25 44.2218 86.6667 49C69.6936 52.9402 61.0989 30.5738 44 33C25.4537 35.6316 19.5189 58.9382 1.33337 65H129.333V1Z"
            fill="url(#paint0_linear_1509_11831)"
          />
          <path
            d="M1.33337 65C19.5189 58.9382 25.4537 35.6316 44 33C61.0989 30.5738 69.6936 52.9402 86.6667 49C107.25 44.2218 108.537 2.73299 129.333 1"
            stroke="#12B76A"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
          <defs>
            <linearGradient
              id="paint0_linear_1509_11831"
              x1="65.3334"
              y1="1"
              x2="65.3334"
              y2="65"
              gradientUnits="userSpaceOnUse"
            >
              <stop offset="0.641167" stop-color="white" stop-opacity="0" />
              <stop offset="1" stop-color="white" />
            </linearGradient>
          </defs>
        </svg>

        <!-- red chart -->
        <svg
          width="131"
          height="66"
          viewBox="0 0 131 66"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
          v-else
        >
          <path
            d="M1.66669 1C22.4626 2.73299 23.7504 44.2218 44.3334 49C61.3065 52.9402 69.9012 30.5738 87 33C105.546 35.6316 111.481 58.9382 129.667 65H1.66669V1Z"
            fill="#FEF3F2"
          />
          <path
            d="M1.66669 1C22.4626 2.73299 23.7504 44.2218 44.3334 49C61.3065 52.9402 69.9012 30.5738 87 33C105.546 35.6316 111.481 58.9382 129.667 65H1.66669V1Z"
            fill="url(#paint0_linear_1509_11813)"
          />
          <path
            d="M129.667 65C111.481 58.9382 105.546 35.6316 87 33C69.9012 30.5738 61.3065 52.9402 44.3334 49C23.7504 44.2218 22.4626 2.73299 1.66668 1"
            stroke="#F04438"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
          <defs>
            <linearGradient
              id="paint0_linear_1509_11813"
              x1="65.6667"
              y1="1"
              x2="65.6667"
              y2="65"
              gradientUnits="userSpaceOnUse"
            >
              <stop offset="0.641167" stop-color="white" stop-opacity="0" />
              <stop offset="1" stop-color="white" />
            </linearGradient>
          </defs>
        </svg>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      required: true,
      type: Object,
    },
  },
};
</script>

<style lang="scss" scoped>
.card {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 24px;
  width: 100%;
  height: 176px;
  background: #ffffff;
  border: 1px solid #eaecf0;
  box-sizing: border-box;
  box-shadow: 0px 1px 3px rgba(16, 24, 40, 0.1),
    0px 1px 2px rgba(16, 24, 40, 0.06);
  border-radius: 8px;
}

.card-heading {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;

  span {
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    color: #101828;
  }
}

.card-info {
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  width: 100%;

  .numbers {
    h4 {
      font-weight: 600;
      font-size: 36px;
      line-height: 44px;
      letter-spacing: -0.02em;
      color: #101828;
      margin: 16px 0px;
    }

    p {
      font-weight: 500;
      font-size: 14px;
      line-height: 20px;
      color: #667085;

      span {
        text-align: center;
        color: #027a48;
        // color: #B42318;
      }
    }
  }
}
</style>
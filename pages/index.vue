<template>
  <div>
    <app-header />
    <sub-header />

    <main class="container">
      <section class="header-section">
        <div>
          <h1>Welcome back, Olivia</h1>

          <p>Track, manage and forecast your customers and orders.</p>
        </div>

        <div class="buttons">
          <button class="secondary-btn">
            <svg
              width="20"
              height="18"
              viewBox="0 0 20 18"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M13.3333 12.3334L10 9.00003M10 9.00003L6.66667 12.3334M10 9.00003V16.5M16.9917 14.325C17.8044 13.8819 18.4465 13.1808 18.8166 12.3322C19.1866 11.4837 19.2635 10.5361 19.0352 9.63893C18.8068 8.74182 18.2862 7.94629 17.5556 7.3779C16.8249 6.80951 15.9257 6.50064 15 6.50003H13.95C13.6978 5.52439 13.2276 4.61864 12.575 3.85085C11.9223 3.08307 11.104 2.47324 10.1817 2.0672C9.25946 1.66116 8.25712 1.46949 7.2501 1.5066C6.24307 1.5437 5.25755 1.80861 4.36765 2.28142C3.47774 2.75422 2.70659 3.42261 2.11218 4.23635C1.51777 5.05008 1.11557 5.98797 0.935814 6.97952C0.756055 7.97107 0.803418 8.99047 1.07434 9.96108C1.34527 10.9317 1.8327 11.8282 2.5 12.5834"
                stroke="#344054"
                stroke-width="1.67"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>

            Import
          </button>

          <button class="primary-btn">
            <svg
              width="14"
              height="14"
              viewBox="0 0 14 14"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M6.99999 1.16669V12.8334M1.16666 7.00002H12.8333"
                stroke="white"
                stroke-width="1.67"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>

            Add
          </button>
        </div>
      </section>

      <section class="metrics">
        <card-metrics
          :data="data"
          v-for="(data, index) in cardMetrics"
          :key="index"
        />
        <!-- <card-metrics :data="cardMetrics" />
        <card-metrics :data="cardMetrics" /> -->
      </section>

      <section class="orders">
        <div class="filter-bar">
          <div class="filters">
            <app-filter-tag text="All Time" />
            <app-filter-tag text="US, AU, +4" />

            <div class="filter-btn">
              <svg
                width="18"
                height="12"
                viewBox="0 0 18 12"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M4 6H14M1.5 1H16.5M6.5 11H11.5"
                  stroke="#344054"
                  stroke-width="1.67"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>

              More filters
            </div>
          </div>

          <div class="filters-mobile">
            <div class="filter-btn">
              <svg
                width="18"
                height="12"
                viewBox="0 0 18 12"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M4 6H14M1.5 1H16.5M6.5 11H11.5"
                  stroke="#344054"
                  stroke-width="1.67"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>

              Edit filters
            </div>

            <div class="tags">
              <app-filter-tag text="All Time" />
              <app-filter-tag text="US, AU, +4" />
            </div>
          </div>
          <app-search />
        </div>

        <div class="table">
          <Companies :companies="companies" />

          <div class="pagination">
            <div class="pagination-buttons">
              <button class="prev">Previous</button>
              <button class="next">Next</button>
            </div>

            <span class="back">
              <svg
                width="14"
                height="14"
                viewBox="0 0 14 14"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M12.8334 7.00002H1.16669M1.16669 7.00002L7.00002 12.8334M1.16669 7.00002L7.00002 1.16669"
                  stroke="#667085"
                  stroke-width="1.67"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>
            </span>

            <span> Page 1 of 10 </span>

            <span class="forward">
              <svg
                width="14"
                height="14"
                viewBox="0 0 14 14"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M1.16669 7.00002H12.8334M12.8334 7.00002L7.00002 1.16669M12.8334 7.00002L7.00002 12.8334"
                  stroke="#667085"
                  stroke-width="1.67"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                />
              </svg>
            </span>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      companies: [
        {
          id: 1,
          name: "Catalog",
          website: "catalogapp.io",
          category: "Content curating app",
          description: "Brings all your news into one place",
          status: "Customer",
          licenseUse: "65",
          totalUsers: 10,
          users: [
            {
              userPfp: "",
            },
          ],
        },
        {
          id: 2,
          name: "Circooles",
          website: "getcirooles.com",
          category: "Design software",
          description: "Super lightweight design app",
          status: "Churned",
          licenseUse: "58",
          totalUsers: 13,
          users: [
            {
              userPfp: "",
            },
          ],
        },
        {
          id: 3,
          name: "Command+R",
          website: "cmdr.ai",
          category: "Data prediction",
          description: "AI and machine learning data",
          status: "Customer",
          licenseUse: "35",
          totalUsers: 7,
          users: [
            {
              userPfp: "",
            },
          ],
        },
        {
          id: 4,
          name: "Hourglass",
          website: "hourglass.app",
          category: "Productivity app",
          description: "Time management and productivity",
          status: "Customer",
          licenseUse: "73",
          totalUsers: 5,
          users: [
            {
              userPfp: "",
            },
          ],
        },
        {
          id: 5,
          name: "Layers",
          website: "getlayers.io",
          category: "Web app integrations",
          description: "Connect web apps seamlessly",
          status: "Churned",
          licenseUse: "27",
          totalUsers: 6,
          users: [
            {
              userPfp: "",
            },
          ],
        },
        {
          id: 6,
          name: "Quotient",
          website: "quotient.co",
          category: "Sales CRM",
          description: "Web-based sales doc management",
          status: "Customer",
          licenseUse: "20",
          totalUsers: 11,
          users: [
            {
              userPfp: "",
            },
          ],
        },
        {
          id: 7,
          name: "Sisyphus",
          website: "sisyphus.com",
          category: "Automation and workflow",
          description: "Time tracking, invoicing and expenses",
          status: "Customer",
          licenseUse: "43",
          totalUsers: 9,
          users: [
            {
              userPfp: "",
            },
          ],
        },
      ],
      cardMetrics: [
        {
          name: "Total customers",
          number: 2420,
          percent: 40,
          positive: true,
        },
        {
          name: "Members",
          number: 1210,
          percent: 10,
          positive: false,
        },
        {
          name: "Active now",
          number: 316,
          percent: 20,
          positive: true,
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
main {
  padding: 48px 0px 96px;

  @media (max-width: 768px) {
    padding: 32px 0px 48px;
  }
}

.header-section {
  display: flex;
  align-items: center;
  justify-content: space-between;

  @media (max-width: 768px) {
    flex-direction: column;
    align-items: flex-start;
    gap: 16px;
  }

  h1 {
    font-weight: 500;
    font-size: 30px;
    line-height: 38px;
    color: #101828;
  }

  p {
    font-weight: normal;
    font-size: 16px;
    line-height: 24px;
    color: #667085;
  }

  .buttons {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 10px;

    button {
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
      padding: 10px 16px;
      gap: 10px;
      border-radius: 8px;
      font-weight: 500;
      font-size: 14px;
      line-height: 20px;
      box-shadow: 0px 1px 2px rgba(16, 24, 40, 0.05);

      &.secondary-btn {
        background: #ffffff;
        border: 1px solid #d0d5dd;
        box-sizing: border-box;
        color: #344054;
      }

      &.primary-btn {
        background: #7f56d9;
        border: 1px solid #7f56d9;
        box-sizing: border-box;
        color: #ffffff;
      }
    }
  }
}

.metrics {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 24px 0px;
  gap: 24px;

  @media (max-width: 768px) {
    flex-direction: column;
    align-items: flex-start;
    gap: 16px;
  }
}

.orders {
  margin: 32px 0px;

  .filter-bar {
    display: flex;
    align-items: center;
    justify-content: space-between;

    @media (max-width: 768px) {
      flex-direction: column;
      align-items: flex-start;
      gap: 12px;
    }

    .filters-mobile {
      display: none;

      @media (max-width: 768px) {
        display: flex;
        order: 2;
        flex-direction: column;
        gap: 12px;
        width: 100%;

        .tags {
          display: flex;
        }

        .filter-btn {
          justify-content: center;
        }
      }
    }

    .filters {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 12px;

      @media (max-width: 768px) {
        display: none;
      }
    }

    .filter-btn {
      padding: 10px 16px;
      background: #ffffff;
      border: 1px solid #d0d5dd;
      box-sizing: border-box;
      box-shadow: 0px 1px 2px rgba(16, 24, 40, 0.05);
      border-radius: 8px;
      display: flex;
      align-items: center;
      gap: 13px;
      cursor: pointer;
    }
  }

  .table {
    margin: 24px 0px;
    background: #ffffff;
    border: 1px solid #eaecf0;
    box-shadow: 0px 4px 8px -2px rgba(16, 24, 40, 0.1),
      0px 2px 4px -2px rgba(16, 24, 40, 0.06);
    border-radius: 8px;
    width: 100%;
    overflow-x: auto;

    .pagination {
      display: flex;
      align-items: center;
      justify-content: space-between;
      height: 66px;
      padding: 24px;

      .back,
      .forward {
        display: none;
        cursor: pointer;

        @media (max-width: 768px) {
          display: block;
        }
      }

      .pagination-buttons {
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 10px;

        @media (max-width: 768px) {
          display: none;
        }

        button {
          padding: 9px 17px;
          background: #ffffff;
          border: 1px solid #d0d5dd;
          box-shadow: 0px 1px 2px rgba(16, 24, 40, 0.05);
          border-radius: 6px;
        }
      }
    }
  }
}
</style>

<template>
  <div>
    <div class="row">
      <Header />
    </div>
    <div class="main-content">
      <div class="main-header">
        <div class="main-header__headings">
          <h3>Poli Overview</h3>
          <p>Welcome Back, Barly</p>
        </div>

        <button class="btn custom-btn-primary">Register Patient</button>
      </div>
      <div class="row">
        <div class="col-sm-12 col-md-6 col-lg-8">
          <div class="row">
            <div class="col-sm-12 col-md-6 col-lg-4">
              <DashboardCard
                :heading="counters[0].title"
                :subHeading="counters[0].value"
                image="mask.svg"
              />
            </div>
            <div class="col-sm-12 col-md-6 col-lg-4">
              <DashboardCard
                :heading="counters[1].title"
                :subHeading="counters[1].value"
                image="stethoscope.svg"
              />
            </div>
            <div class="col-sm-12 col-md-6 col-lg-4">
              <DashboardCard
                :heading="counters[2].title"
                :subHeading="counters[2].value"
                image="first-aid-box1.svg"
              />
            </div>
          </div>

          <div class="row chart-area mt-3">
            <div class="d-flex justify-content-between align-items-center my-3">
              <h5 class="heading-primary">Patient Covid Static</h5>
              <div class="chart-buttons">
                <button class="active">Month</button>
                <button>Weekly</button>
              </div>
            </div>
            <Areachart
              :categories="covidReport.categories"
              :values="covidReport.values"
              :lablel="covidReport.types"
            />
          </div>

          <div class="row mt-3">
            <div class="col-sm-12 col-md-6 col-lg-6 mr-2">
              <div class="d-flex justify-content-between align-items-center my-3">
                <h5 class="heading-primary">{{reportByGender[0].title}}</h5>
              </div>
              <DountChart
                :seriess="reportByGender[0].values"
                :lables="reportByGender[0].types"
                :colors="['#e0edff' ,'#005aff']"
              />
            </div>
            <div class="col-sm-12 col-md-6 col-lg-6">
              <div class="d-flex justify-content-between align-items-center my-3">
                <h5 class="heading-primary">{{reportByGroup[0].title}}</h5>
              </div>
              <DountChart
                :seriess="reportByGroup[0].values"
                :lables="reportByGroup[0].types"
                :colors="['#00e4e1','#005aff','#e0edff' ]"
              />
            </div>
          </div>
        </div>
        <div class="col-sm-12 col-md-6 col-lg-4">
          <div class="rightside">
            <h5 class="heading-primary">Informations</h5>
            <select class="rightside__celendermonth" name="months">
              <option value="jan">January</option>
              <option value="feb">February</option>
              <option value="mar">March</option>
              <option value="apr">April</option>
              <option value="may">May</option>
              <option value="june" selected>June</option>
              <option value="july">July</option>
              <option value="aug">August</option>
              <option value="sep">September</option>
              <option value="oct">October</option>
              <option value="nov">November</option>
              <option value="dec">December</option>
            </select>

            <ul class="rightside__celenderweek">
              <li>
                Mon
                <span>16</span>
              </li>
              <li>
                Tues
                <span>17</span>
              </li>
              <li class="active">
                Wed
                <span class="event">18</span>
              </li>
              <li>
                Thu
                <span class="event">19</span>
              </li>
              <li>
                Fri
                <span>20</span>
              </li>
              <li>
                Sat
                <span>21</span>
              </li>
              <li>
                Sun
                <span>22</span>
              </li>
            </ul>

            <div class="row mt-2 mx-2">
              <h5 class="heading-primary">Appoinment List</h5>
              <div class="appoinment-card">
                <div class="appoinment-card-inner">
                  <div class="appoinment-card-inner__image-container">
                    <img src="../../assets/icons/covid blue.png" />
                  </div>
                  <div class="appoinment-card-inner__content">
                    <h5 class="card__heading">Covid Swap Test</h5>
                    <p class="card__subheading">8:00 AM - 4:00PM</p>
                    <p class="card__tursery">128 Participents</p>

                    <div class="members">
                      <ul class="p-0 m-0">
                        <li class="d-inline-block pink">MR</li>
                        <li class="d-inline-block blue">HZ</li>
                        <li class="d-inline-block pink">Aw</li>
                        <li class="d-inline-block">+2</li>
                      </ul>
                    </div>
                  </div>
                </div>
              </div>

              <div class="appoinment-card mt-2">
                <div class="appoinment-card-inner">
                  <div class="appoinment-card-inner__image-container">
                    <img src="../../assets/icons/covid blue.png" />
                  </div>
                  <div class="appoinment-card-inner__content">
                    <h5 class="card__heading">Covid Rapid Test</h5>
                    <p class="card__subheading">9:00 AM - 5:00PM</p>
                    <p class="card__tursery">240 Participents</p>

                    <div class="members">
                      <ul class="p-0 m-0">
                        <li class="d-inline-block pink">MR</li>
                        <li class="d-inline-block blue">HZ</li>
                        <li class="d-inline-block pink">Aw</li>
                        <li class="d-inline-block">+2</li>
                      </ul>
                    </div>
                  </div>
                </div>
              </div>

              <div class="row mt-2">
                <div class="cilinic__card">
                  <h5 class="heading-primary">Poloclinic Division</h5>

                  <div class="cilinic__card--content">
                    <div class="cilinic__card--content-conatinerimage">
                      <img src="../../assets/icons/covid blue.png" />
                    </div>
                    <div class="cilinic__card--content-text">
                      <h5 class="card__heading">Dental Polyclinic</h5>
                      <p class="card__subheading">Open 7:00 AM - 11:00PM</p>
                    </div>
                  </div>
                  <div class="cilinic__card--content">
                    <div class="cilinic__card--content-conatinerimage">
                      <img src="../../assets/icons/covid blue.png" />
                    </div>
                    <div class="cilinic__card--content-text">
                      <h5 class="card__heading">Cardiac Polyclinic</h5>
                      <p class="card__subheading">Open 7:00 AM - 11:30PM</p>
                    </div>
                  </div>
                  <div class="cilinic__card--content">
                    <div class="cilinic__card--content-conatinerimage">
                      <img src="../../assets/icons/covid blue.png" />
                    </div>
                    <div class="cilinic__card--content-text">
                      <h5 class="card__heading">Radiology polyclinic</h5>
                      <p class="card__subheading">Open 7:00PM - 11:00AM</p>
                    </div>
                  </div>
                  <div class="row mt1">
                    <button class="cilinic__card--button">See More Polyclinic</button>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Areachart from "../UI/Areachart.vue";
import DashboardCard from "../UI/DashboardCard.vue";
import DountChart from "../UI/DountChart.vue";
import Header from "./Header.vue";
import axios from "axios";

export default {
  name: "Main",
  components: {
    Header,
    DashboardCard,
    Areachart,
    DountChart,
  },
  data() {
    return {
      counters: [],
      covidReport: {},
      reportByGender: [],
      reportByGroup: [],
    };
  },
  mounted() {
    let config = {
      headers: {
        "Content-Type": "application/json",
        Accept: "application/json",
      },
    };
    axios
      .get("https://apitest.iqfulfillment.com/v1/test/dashboard", config)
      .then((res) => {
        console.log(res);
        (this.counters = res.data.counters),
          (this.covidReport = res.data["covid_report"]),
          (this.reportByGender = res.data["report_by_gender"]),
          (this.reportByGroup = res.data["report_by_group"]);
      })
      .catch((err) => {
        console.log(err);
      });
  },
};
</script>


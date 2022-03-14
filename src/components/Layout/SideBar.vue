<template>
  <div class="sidebar">
    <div>
      <img src="../../assets/logo.png" class="sidebar__logo" alt="app-logo" />
      <div class="sidebar__menubar">
        <ul>
          <h5>Management</h5>
          <li class="active">
            <img src="../../assets/icons/grid.svg" alt="icon" />
            <a href="#">overview</a>
          </li>
          <li>
            <img src="../../assets/icons/charts.svg" alt="icon" />

            <a href="#">statistics</a>
          </li>
          <li>
            <img src="../../assets/icons/meter.svg" alt="icon" />
            <a href="#">patients</a>
          </li>
          <li>
            <img src="../../assets/icons/clinic.svg" alt="icon" />
            <a href="#">polyclinic</a>
          </li>
          <li>
            <img src="../../assets/icons/doctors.svg" alt="icon" />
            <a href="#">Doctors</a>
          </li>
          <li>
            <img src="../../assets/icons/mediciens.svg" alt="icon" />
            <a href="#">Medicines</a>
          </li>
          <h5>Support</h5>
          <li>
            <img src="../../assets/icons/message.svg" alt="icon" />
            <a href="#">Messages</a>
          </li>

          <li>
            <img src="../../assets/icons/setting.svg" alt="icon" />
            <a href="#">Settings</a>
          </li>
        </ul>
      </div>
    </div>

    <div class="sidebar__bottom">
      <div class="card">
        <h5 class="card__heading">Covid Informations</h5>
        <div class="card__link">
          <img src="../../assets/icons/gloab.svg" alt />
          <span>World</span>
        </div>
        <div class="card__list">
          <ul>
            <li>
              Infected -
              <span>8.119.575</span>
            </li>
            <li>
              Recovered -
              <span>4.231.974</span>
            </li>
            <li>
              Deaths -
              <span>493.217</span>
            </li>
          </ul>
        </div>
        <div class="card__button">
          <button>Check Covid</button>
        </div>
      </div>
      <div class="sidebar__bottom--footer">
        <div class="heading">© Poli Clinic. 2020</div>
        <div class="sub-heading">Poli Clinic is medical management for all doctors, patient & Staff.</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SideBar",
};
</script>


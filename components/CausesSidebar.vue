<template>
  <div class="causes-details__right">
    <div class="causes-details__organizer">
      <div class="causes-details__organizer-img">
        <img
          src="~/assets/images/resources/causes-details-organizar-img-1.jpg"
          alt=""
        />
      </div>
      <div class="causes-details__organizer-content">
        <h5>{{ nombre }}</h5>
        <ul class="causes-details__organizer-list list-unstyled">
          <li><i class="fas fa-map-marker-alt"></i>{{ direccion}}</li>
          <li><i class="fas fa-map-marker-alt"></i>{{ ciudad }}</li>
        </ul>
      </div>
    </div>
    <!-- <div class="causes-details__donations">
      <h3 class="causes-details__donations-title">Mas huertas</h3>
      <ul class="list-unstyled causes-details__donations-list">
        <li>
          <div class="causes-details__donations-img">
            <img
              src="~/assets/images/resources/recent-donation-img-1.jpg"
              alt=""
            />
          </div>
          <div class="causes-details__donations-content">
            <h4>$20</h4>
            <h5>David Marks <span>3 hours ago</span></h5>
            <p>God bless you dear</p>
          </div>
        </li>
        <li>
          <div class="causes-details__donations-img">
            <img
              src="~/assets/images/resources/recent-donation-img-2.jpg"
              alt=""
            />
          </div>
          <div class="causes-details__donations-content">
            <h4>$60</h4>
            <h5>Jessica Rose <span>6 hours ago</span></h5>
            <p>God bless you dear</p>
          </div>
        </li>
        <li>
          <div class="causes-details__donations-img">
            <img
              src="~/assets/images/resources/recent-donation-img-3.jpg"
              alt=""
            />
          </div>
          <div class="causes-details__donations-content">
            <h4>$30</h4>
            <h5>Kevim Martin <span>1 day ago</span></h5>
            <p>God bless you dear</p>
          </div>
        </li>
        <li>
          <div class="causes-details__donations-img">
            <img
              src="~/assets/images/resources/recent-donation-img-4.jpg"
              alt=""
            />
          </div>
          <div class="causes-details__donations-content">
            <h4>$180</h4>
            <h5>Anonymous <span>1 day ago</span></h5>
            <p>God bless you dear</p>
          </div>
        </li>
      </ul>
    </div> -->
  </div>
</template>
<script>
export default{
  props:{
    nombre:{
      type: String
    },
    direccion:{type: String},
    ciudad:{type: String}
  }
}

</script>
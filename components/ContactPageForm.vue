<template>
  <!--Contact page Start-->
  <section class="contact-page">
    <div class="container">
      <div class="section-title text-center">
        <span class="section-title__tagline">Contacto</span>
        <!-- <h2 class="section-title__title">
          We love to hear from our <br />
          happy customers
        </h2> -->
      </div>
      <div class="row">
        <div class="col-xl-6 col-lg-6">
          <div class="contact-page__left">
            <!-- <div class="contact-page__img">
              <img src="~images/resources/contact-page-img-1.jpg" alt="" />
            </div> -->
            <!-- <p class="contact-page__text">
              There are many variations of passages of available but the
              majority have suffered alteration in some form, by injected humou
              or randomised words even slightly believable.
            </p> -->
            <div class="contact-page__contact-info">
              <ul class="contact-page__contact-list list-unstyled">
                <li>
                  <div class="icon">
                    <span class="icon-chat"></span>
                  </div>
                  <div class="text">
                    <p>Llamanos</p>
                    <a href="tel:+573197560332">+57 3197560332</a>
                  </div>
                </li>
                <li>
                  <div class="icon">
                    <span class="icon-message"></span>
                  </div>
                  <div class="text">
                    <p>Coreo</p>
                    <a href="mailto:gerencia@pacamama.com.co"
                      >gerencia@pacamama.com.co</a
                    >
                  </div>
                </li>
                <!-- <li>
                  <div class="icon">
                    <span class="icon-address"></span>
                  </div>
                  <div class="text">
                    <p>Visit Office</p>
                    <h5>80 broklyn golden street</h5>
                  </div>
                </li> -->
              </ul>
            </div>
          </div>
        </div>
        <div class="col-xl-6 col-lg-6">
          <div class="contact-page__form">
            <form
              action="#"
              class="contact-page__main-form contact-form-validated"
            >
              <div class="row">
                <div class="col-xl-12">
                  <div class="contact-page__input-box">
                    <input type="text" placeholder="Nombre" name="name" />
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-xl-6">
                  <div class="contact-page__input-box">
                    <input
                      type="email"
                      placeholder="Correo"
                      name="email"
                    />
                  </div>
                </div>
                <div class="col-xl-6">
                  <div class="contact-page__input-box">
                    <input type="text" placeholder="Asunto" name="subject" />
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-xl-12">
                  <div class="contact-page__input-box">
                    <input
                      type="text"
                      placeholder="Telefono"
                      name="phone"
                    />
                  </div>
                </div>
                <div class="col-xl-12">
                  <div class="contact-page__input-box">
                    <textarea
                      name="message"
                      placeholder="Mensaje"
                    ></textarea>
                  </div>
                  <button type="submit" class="thm-btn contact-page__btn">
                    <i class="fas fa-arrow-circle-right"></i>Enviar
                  </button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>
  <!--Contact page End-->
</template>

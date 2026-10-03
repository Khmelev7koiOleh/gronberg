<script setup lang="ts">
import { useParallax } from "~/composables/useParallax";
import { useIntersection } from "@/composables/useIntersection";

const { target: latestTarget, isVisible: latestVisible } =
  useIntersection(0.15);

const { target: heroTarget, isVisible: heroVisible } = useIntersection(0.15);
const { target: servicesTarget, isVisible: servicesVisible } =
  useIntersection(0.15);

const { target: exhibitionsTarget, isVisible: exhibitionsVisible } =
  useIntersection(0.15);

const { target: reviewsTarget, isVisible: reviewsVisible } =
  useIntersection(0.15);

const latestSection1 = ref<HTMLElement | null>(null);
const latestItem1 = ref<HTMLElement | null>(null);
const latestItem2 = ref<HTMLElement | null>(null);
const latestItem3 = ref<HTMLElement | null>(null);
const latestItem4 = ref<HTMLElement | null>(null);
useParallax(latestSection1, latestItem1, -0.4);
useParallax(latestSection1, latestItem2, -0.2);
useParallax(latestSection1, latestItem3, -0.2);
useParallax(latestSection1, latestItem4, -0.4);
</script>
<template>
  <div class="hero">
    <div class="hero__container" ref="heroTarget">
      <div class="hero__content content">
        <div class="content__body" :class="{ 'is-show': heroVisible }">
          <div class="content__title">
            Jacob <br />
            <span>Grønberg</span>
          </div>
          <div class="content__subtitle">
            Photographer <br />

            <span> & Visual artist </span>
          </div>
        </div>
        <div class="content__author author">
          <div class="author__body">
            <img class="author__photo" src="/hero/author.jpg" alt="" />
            <div class="author__text">Hi, Im Jacob</div>
          </div>
          <a href="#" class="author__action"
            >Work <br />
            With Me</a
          >
        </div>
      </div>
      <div class="hero__body body">
        <img class="body__photo" src="/hero/work.jpg" alt="" />

        <div class="body__scrolldown scrolldown">
          <span>
            Scroll Down <br />
            & Explore</span
          >
        </div>
      </div>
    </div>
    <!-- <div class="hero__one">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima repellat
      amet totam rem ea facere voluptate alias quod, debitis iure dignissimos
      quaerat doloribus, sunt incidunt molestiae, ut necessitatibus? Eaque, quo?
    </div>
    <br></br>
    <div class="hero__two">
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima repellat
      amet totam rem ea facere voluptate alias quod, debitis iure dignissimos
      quaerat doloribus, sunt incidunt molestiae, ut necessitatibus? Eaque, quo?
    </div> -->
  </div>

  <div class="services">
    <div class="services__container">
      <div
        class="services__body"
        ref="servicesTarget"
        :class="{ 'is-show': servicesVisible }"
      >
        <h2 class="services__title">Services</h2>
        <ol class="services__list">
          <li class="services__item">
            <div class="services__item-title">Photo shooting</div>
            <div class="services__item-description">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam
              voluptatum, quod, quia, voluptates quibusdam quas voluptatibus
              quibusdam quae quos.
            </div>
          </li>
          <li class="services__item">
            <div class="services__item-title">Video editing</div>
            <div class="services__item-description">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam
              voluptatum, quod, quia, voluptates quibusdam quas voluptatibus
              quibusdam quae quos.
            </div>
          </li>
          <li class="services__item">
            <div class="services__item-title">Art direction</div>
            <div class="services__item-description">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam
              voluptatum, quod, quia, voluptates quibusdam quas voluptatibus
              quibusdam quae quos.
            </div>
          </li>
        </ol>
      </div>
    </div>
  </div>

  <div class="latest">
    <TitleComponent title-one="Latest" title-two="Works" />
    <div
      class="latest__container"
      ref="latestTarget"
      :class="{ 'is-show': latestVisible }"
    >
      <div ref="latestSection1" class="latest__items">
        <div class="latest__column">
          <article ref="latestItem1" class="latest__item item-latest">
            <a href="#" class="item-latest__link">
              <h2 class="item-latest__title">
                Dancing in Black & <span>White</span>
              </h2>

              <figure class="item-latest__media">
                <img src="/latest/1.jpg" alt="Work Title" />
                <figcaption class="item-latest__caption">
                  New York <br />
                  October 2021
                </figcaption>
              </figure>
            </a>
          </article>

          <acticle ref="latestItem2" class="latest__item item-latest">
            <a href="#" class="item-latest__link">
              <h2 class="item-latest__title">Week <span>Fashion</span></h2>

              <figure class="item-latest__media">
                <img
                  class="item-latest__image"
                  src="/latest/2.jpg"
                  alt="Work Title"
                />
                <figcaption class="caption">
                  New York <br />
                  October 2021
                </figcaption>
              </figure>
            </a>
          </acticle>
        </div>

        <div class="latest__column">
          <acticle ref="latestItem3" class="latest__item item-latest">
            <a href="#" class="item-latest__link">
              <h2 class="item-latest__title">Style <span>& Fashion </span></h2>

              <figure class="item-latest__media">
                <img src="/latest/3.jpg" alt="Work Title" />
                <figcaption class="item-latest__caption">
                  New York <br />
                  October 2021
                </figcaption>
              </figure>
            </a>
          </acticle>

          <acticle ref="latestItem4" class="latest__item item-latest">
            <a href="#" class="item-latest__link">
              <h2 class="item-latest__title">One <span>Eye</span></h2>

              <figure class="item-latest__media">
                <img src="/latest/4.jpg" alt="Work Title" />
                <figcaption class="caption">
                  New York <br />
                  October 2021
                </figcaption>
              </figure>
            </a>
          </acticle>
        </div>
      </div>
    </div>
  </div>

  <div class="exhibitions">
    <TitleComponent title-one="Exhibitions" title-two="'22" />

    <div
      class="exhibitions__container"
      ref="exhibitionsTarget"
      :class="{ 'is-show': exhibitionsVisible }"
    >
      <ul class="exhibitions__list">
        <li class="exhibitions__item item-exhibitions">
          <div class="item-exhibitions__media">
            <img
              class="item-exhibitions__image"
              src="/exhibitions/1.jpg"
              alt="Work Title"
            />
          </div>
          <div class="item-exhibitions__content">
            <div class="item-exhibitions__body">
              <div class="item-exhibitions__place">
                <span>New York</span> <span>Townhall</span> <span>2022</span>
              </div>
              <div class="item-exhibitions__title">
                Independent <span>Beauty</span>
              </div>
              <div class="item-exhibitions__text">
                <p>
                  Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed
                  diam nonumy eirmod tempor invidunt ut labore et dolore magna
                  aliquyam erat, sed diam voluptua.
                </p>
              </div>
            </div>

            <a href="#" class="item-exhibitions__buy">
              <span>Buy Ticket</span>

              <svg
                width="21"
                height="21"
                viewBox="0 0 21 21"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path d="M4.94971 15.9099L15.5563 5.30326" />
                <path d="M6.01025 4.9499H15.9097V14.8494" />
              </svg>
            </a>
          </div>
          <div class="item-exhibitions__date">
            <time datetime="2022-06-16">
              <small>Jun</small> <span class="">16</span>
            </time>
          </div>
        </li>
        <li class="exhibitions__item item-exhibitions">
          <div class="item-exhibitions__media">
            <img
              class="item-exhibitions__image"
              src="/exhibitions/2.jpg"
              alt="Work Title"
            />
          </div>
          <div class="item-exhibitions__content">
            <div class="item-exhibitions__body">
              <div class="item-exhibitions__place">
                <span>Berlin </span> <span>Kunsthalle</span> <span>2022</span>
              </div>
              <div class="item-exhibitions__title">
                In Humanity We
                <span>Trust</span>
              </div>
              <div class="item-exhibitions__text">
                <p>
                  Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed
                  diam nonumy eirmod.
                </p>
              </div>
            </div>

            <a href="#" class="item-exhibitions__buy">
              <span>Buy Ticket</span>

              <svg
                width="21"
                height="21"
                viewBox="0 0 21 21"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path d="M4.94971 15.9099L15.5563 5.30326" />
                <path d="M6.01025 4.9499H15.9097V14.8494" />
              </svg>
            </a>
          </div>
          <div class="item-exhibitions__date">
            <time datetime="2022-06-16">
              <small>Mar</small> <span class="">02</span>
            </time>
          </div>
        </li>

        <li class="exhibitions__item item-exhibitions">
          <div class="item-exhibitions__media">
            <img
              class="item-exhibitions__image"
              src="/exhibitions/3.jpg"
              alt="Work Title"
            />
          </div>
          <div class="item-exhibitions__content">
            <div class="item-exhibitions__body">
              <div class="item-exhibitions__place">
                <span>Berlin </span> <span>Kunsthalle</span> <span>2022</span>
              </div>
              <div class="item-exhibitions__title">
                Berlin AT
                <span>Night</span>
              </div>
              <div class="item-exhibitions__text">
                <p>
                  Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed
                  diam nonumy eirmod tempor invidunt ut labore et dolore.
                </p>
              </div>
            </div>

            <a href="#" class="item-exhibitions__buy">
              <span>Buy Ticket</span>

              <svg
                width="21"
                height="21"
                viewBox="0 0 21 21"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path d="M4.94971 15.9099L15.5563 5.30326" />
                <path d="M6.01025 4.9499H15.9097V14.8494" />
              </svg>
            </a>
          </div>
          <div class="item-exhibitions__date">
            <time datetime="2022-06-16">
              <small>Feb</small> <span class="">01</span>
            </time>
          </div>
        </li>
      </ul>
    </div>
  </div>

  <!-- reviews -->

  <div
    class="reviews"
    ref="reviewsTarget"
    :class="{ 'is-show': reviewsVisible }"
  >
    <div class="reviews__container">
      <div class="reviews__header header-reviews">
        <div class="reviews__header header-reviews__body">
          <h2 class="header-reviews__title">
            What my Clients <span>Say</span>
          </h2>
          <h3 class="header-reviews__subtitle">
            Worked with Over <span>50 clients</span> around the world
          </h3>

          <NuxtLink to="/" class="header-reviews__link">
            <span class="header-reviews__link-text">Work With Me</span>
            <svg
              class="header-reviews__link-icon"
              width="32"
              height="15"
              viewBox="0 0 32 15"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path d="M0 7.35352H30" />
              <path d="M23.5 0.353516L30.5 7.35352L23.5 14.3535" />
            </svg>
          </NuxtLink>
        </div>
      </div>
      <ul class="reviews__list">
        <li class="reviews__item item-reviews">
          <div class="item-reviews__media">
            <img
              class="item-reviews__image"
              src="/reviews/1.jpg"
              alt="Work Title"
            />
          </div>

          <div class="item-reviews__body">
            <div class="item-reviews__title-container">
              <img src="/reviews/odqm.svg" alt="" class="item-reviews__image" />
              <h3 class="item-reviews__title">
                I Really Enjoyed Working With Jacob
              </h3>
            </div>

            <div class="item-reviews__text">
              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
                eiusmod tempor incididunt ut labore et dolore magna aliqua.
              </p>
              <p>
                Enim lobortis scelerisque fermentum dui faucibus in ornare quam
                viverra. Laoreet sit amet cursus sit amet dictum sit amet justo.
              </p>
            </div>

            <div class="item-reviews__author">
              <span>Michelle Lindstrøm </span><span> Photoshoot</span>
            </div>
          </div>
        </li>
        <li class="reviews__item item-reviews">
          <div class="item-reviews__media">
            <img
              class="item-reviews__image"
              src="/reviews/2.jpg"
              alt="Work Title"
            />
          </div>

          <div class="item-reviews__body">
            <div class="item-reviews__title-container">
              <img src="/reviews/odqm.svg" alt="" class="item-reviews__image" />
              <h3 class="item-reviews__title">
                I Really Enjoyed Working With Jacob
              </h3>
            </div>

            <div class="item-reviews__text">
              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
                eiusmod tempor incididunt ut labore et dolore magna aliqua.
              </p>
            </div>

            <div class="item-reviews__author">
              <span>Jannis Jackson </span><span> Art Direction </span>
            </div>
          </div>
        </li>
        <li class="reviews__item item-reviews">
          <div class="item-reviews__media">
            <img
              class="item-reviews__image"
              src="/reviews/3.jpg"
              alt="Work Title"
            />
          </div>

          <div class="item-reviews__body">
            <div class="item-reviews__title-container">
              <img src="/reviews/odqm.svg" alt="" class="item-reviews__image" />
              <h3 class="item-reviews__title">
                I Really Enjoyed Working With Jacob
              </h3>
            </div>

            <div class="item-reviews__text">
              <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
                eiusmod tempor incididunt ut labore et dolore magna aliqua. Enim
                lobortis scelerisque fermentum dui faucibus in ornare quam
                viverra.
              </p>
            </div>

            <div class="item-reviews__author">
              <span>Daniela Berg </span><span> Video Editing</span>
            </div>
          </div>
        </li>
      </ul>
    </div>
  </div>

  <div class="letswork">
    <div class="letswork__container">
      <div class="letswork__body">
        <a href="#" class="letswork__figure"
          >Get In <br />
          Touch</a
        >

        <h2 class="letswork__title">Lets Work <br /><span>Together</span></h2>
      </div>
    </div>
  </div>
</template>

<style scoped></style>

<template>
  <header class="header">
    <h1 class="title">
      <span>Front-end</span>
      <span>Developer</span>
      <span>Socratone</span>
    </h1>
    <p class="text">
      <span>같은 문제를 반복하지 않기 위해 모든 것을</span>
      <span>정리하고 기록하는 Front-end 개발자</span>
    </p>
    <address class="linkWrap">
      <button class="linkButton" @click="handlePhoneClick">
        <p><PhoneIcon size="30" color="whitesmoke" /></p>
        <p class="linkText">Phone</p>
      </button>
      <p class="contact" :style="{ width: phoneNumberWidth }">
        {{ phone }}
      </p>
      <button class="linkButton" @click="handleEmailClick">
        <p><EmailIcon size="30" color="whitesmoke" /></p>
        <p class="linkText">Email</p>
      </button>
      <p class="contact" :style="{ width: emailWidth }">
        {{ email }}
      </p>
      <a 
        class="linkButton"
        rel="noreferrer"
        href="https://github.com/socratone" 
        target="_blank"
      >
          <p><GithubIcon size="30" color="whitesmoke" /></p>
          <p class="linkText">Github</p>
      </a>
      <a 
        class="linkButton" 
        rel="noreferrer"
        href="https://thinkforthink.tistory.com/" 
        target="_blank"
      >
          <p><BlogIcon size="30" color="whitesmoke" /></p>
          <p class="linkText">Blog</p>
      </a>
    </address>
    <picture>
      <source 
        type="image/webp" 
        srcset="~/assets/images/portfolio/profile@2x.webp" 
      />
      <source 
        type="image/png" 
        srcset="~/assets/images/portfolio/profile.png" 
      />
      <img 
        src="~/assets/images/portfolio/profile.png" 
        alt="profile"
        width="200"
        class="profile"
      />
    </picture>
    <picture>
      <source 
        type="image/webp" 
        srcset="~/assets/images/portfolio/desk@2x.webp" 
      />
      <source 
        type="image/png" 
        srcset="~/assets/images/portfolio/desk.png" 
      />
      <img 
        src="~/assets/images/portfolio/desk.png" 
        alt="desk"
        class="desk"
      />
    </picture>
  </header>
</template>

<script>
import PhoneIcon from "../icon/PhoneIcon.vue"
import EmailIcon from "../icon/EmailIcon.vue"
import GithubIcon from "../icon/GithubIcon.vue"
import BlogIcon from "../icon/BlogIcon.vue"

export default {
  components: {
    PhoneIcon,
    EmailIcon,
    GithubIcon,
    BlogIcon
  },
  data() {
    return {
      phoneNumberWidth: '0',
      emailWidth: '0'
    }
  },
  computed: {
    phone() {
      return process.env.PHONE;
    },
    email() {
      return process.env.EMAIL;
    }
  },
  methods: {
    handlePhoneClick() {
      if (this.phoneNumberWidth !== '13.5rem') this.phoneNumberWidth = '13.5rem';
      else this.phoneNumberWidth = '0';
    },
    handleEmailClick() {
      if (this.emailWidth !== '19.5rem') this.emailWidth = '19.5rem';
      else this.emailWidth = '0';
    }
  }
}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Goldman&display=swap');

p {
  margin: 0;
}

.header {
  background: var(--color-background-primary);
  padding: 60px 0 0 0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.title {
  font-family: 'Goldman', cursive;
  font-size: 4.2rem;
  font-weight: 400;
  color: #f5f5f5;
  margin-bottom: 0 0 10px 0;

  span {
    margin: 0 12px 0 0;
    &:last-child {
      margin: 0;
    }
  }

  @media (max-width: 750px) {
    display: flex;
    flex-direction: column;
    align-items: center;
    span {
      margin: 0;
    }
  }
}

.text {
  font-size: 1.7rem;
  font-weight: 400;
  text-align: center;
  color: #f5f5f5;
  margin: 0 0 22px 0;

  span {
    margin: 0 4px 0 0;
    &:last-child {
      margin: 0;
    }
  }

  @media (max-width: 750px) {
    display: flex;
    flex-direction: column;
    align-items: center;
    span {
      margin: 0 0 10px 0;
      &:last-child {
        margin: 0;
      }
    }
  }
}

.linkWrap {
  display: flex;
  justify-content: center;
  margin-bottom: 50px;
}

.linkButton {
  color: #f5f5f5;
  display: flex;
  align-items: center;
  margin: 0 10px;
  font-style: italic;
  cursor: pointer;
 
  p:last-child {
    margin-left: 5px;
  }
}

.linkText {
  font-size: 1.6rem;

  @media (max-width: 750px) {
    display: none;
  }
}

.contact {
  width: 0;
  white-space: nowrap;
  overflow: hidden;
  color: #fdc073;
  display: flex;
  align-items: center;
  transition: width 0.5s;
}

.profile {
  width: 200px;
  border-radius: 100px;
  margin-bottom: 50px;
}

.desk {
  display: block;
  width: 100%;
  max-width: 490px;
  padding: 0 20px;
  box-sizing: border-box;
}
</style>
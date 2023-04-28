<template>
    <div>
        <Navbar></Navbar>
        <main>
            <Nuxt />
        </main>
        <Footer></Footer>
    </div>
</template>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Roboto&family=Roboto+Condensed&display=swap');

  :root {
    --color-black: #2D333C;
    --color-white: #fff;
    --color-primary: #00C95A;
    --color-secondary: #0768FB;

    --font-family-primary: 'Roboto', sans-serif;
    --font-family-secondary: 'Roboto Condensed', sans-serif;

    --image-box-shadow: -10px -10px 0px var(--color-primary), 10px 10px 0px var(--color-black);

    --border-radius: 1px;
  }
  @media screen and (min-width: 0px) {
    * {
      font-family: var(--font-family-primary);
    }
    html {
        overflow-x: hidden;
        font-size: 62.5%;
        @media screen and (min-width: 112.5em) {
            font-size: 75%;
        }
        
        @media screen and (min-width: 85.375em) and (max-width: 75em) {
            font-size: 56.25%;
        }
        
        @media screen and (max-width: 56.25em) {
            font-size: 50%;
        }
        
        @media screen and (max-width: 28.125em) {
            font-size: 45%;
        }
    }
    body {
        margin: 0;
        background-color: #2D333C;
    }
    h1, h2, h3 {
        margin: 0;
        font-family: var(--font-family-secondary);
    }
    h1 {
        font-size: 8rem;
    }
    h2 {
        font-size: 6rem;
    }
    h3 {
        font-size: 3rem;
    }
    p {
        font-size: 16px;
    }
    .button {
        text-decoration: none;
        background-color: var(--color-primary);
        color: var(--color-black);
        border: none;
        font-size: 16px;
        font-family: var(--font-family-secondary);
        text-transform: uppercase;
        letter-spacing: 2px;
        display: block;
        width: 100%;
        text-align: center;
        padding: 1.6rem 0;
        border-radius: var(--border-radius);
        transition: all 0.1s ease;
        cursor: pointer;
        &:hover {
            color: var(--color-white);
        }
    }
    .text-highlight {
        color: var(--color-primary) !important;
    }
    .py {
        padding-top: 10rem;
        padding-bottom: 10rem;
    }
    .px {
        padding-left: 4rem;
        padding-right: 4rem;
    }
    .section-header-top {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
    }
    .header-bar {
        background-color: var(--color-primary);
        display: block;
        height: 1px;
    }
  }
  @media screen and (min-width: 768px) {
    .px {
        padding-left: 12rem;
        padding-right: 12rem;
    }
    .button {
        width: 30rem;
    }
  }
  @media screen and (min-width: 1180px) {
    .px {
        padding-left: 25rem;
        padding-right: 25rem;
    }
  }
  @media screen and (min-width: 1400px) {
    .px {
        padding-left: 35rem;
        padding-right: 35rem;
    }
  }
  @media screen and (min-width: 1800px) {
    .px {
        padding-left: 40rem;
        padding-right: 40rem;
    }
  }
</style>
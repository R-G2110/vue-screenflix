<script>
export default {
  name: "CallToAction",
};
</script>

<template>
  <div class="cta">
    <div class="container">
      <h2>Still looking for something to watch?</h2>
      <p>Check out our full library</p>
      <button class="cta-btn">View all</button>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.cta {
  margin-top: 200px;
  padding: 60px 20px;
  background-color: var(--color-red);
  text-align: center;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);

  h2 {
    font-size: 2rem;
    margin-bottom: 15px;
  }

  p {
    font-size: 1.2rem;
    margin-bottom: 20px;
  }

  .cta-btn {
    color: var(--color-red); 
    border: none;
    padding: 10px 30px;
    font-size: 1rem;
    font-weight: bold;
    cursor: pointer;
    transition: background 0.5s ease-in-out, color 0.5s ease-in-out;

    &:hover {
      background-color: var(--color-gray-dark); 
    }
  }
}
</style>

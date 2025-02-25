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
  height: 360px;
  margin-top: 200px;
  padding: 60px 20px;
  background-color: var(--color-red);
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
  
  .container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

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
    transition: all 0.3s ease;
    outline: 1px solid var(--color-gray-dark);
    outline-offset: -5px;
    
    &:hover {
      outline: 2px solid var(--color-white);
      outline-offset: 0px;
      background-color: var(--color-gray-dark); 
    }
  }
}
</style>

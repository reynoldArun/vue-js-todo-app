<template>
  <div class="list">
      <p>{{todo}} <button @click="$emit('delete-item')">Delete</button></p>
  </div>
</template>

<script>
export default {
    props: ['todo']
}
</script>

<style>
    .list {
        text-align: left;
        text-transform: capitalize;
    }
    
    .list > p {
        width: 16.875rem;
        height: 2.5rem;
        background: green;
        margin: 20px auto;
        display: flex;
        justify-content: space-between;
        padding: 0rem 2rem;
        align-items: center;
        color: white;
    }

    .list > p > button {
        width: 3.125rem;
        height: 1.5625rem;
        border: none;
        background: #35495E;
        color: white;
        cursor: pointer;
    }

    @media only screen and (min-width: 37.5rem) {
        .list > p {
            width: 29.375rem;
        }
    }

</style>
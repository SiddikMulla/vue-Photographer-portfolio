<template>
  <div class="testimonials">
    <div v-for="testimonial in testimonials" :key="testimonial.id" class="card">
      <img
        :src="testimonial.image"
        alt="Testimonial Image"
        class="card-image"
      />
      <div class="card-text">
        <h3 class="card-title">{{ testimonial.name }}</h3>
        <p class="card-description">{{ testimonial.message }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CustomerTestimonial",
  data() {
    return {
      testimonials: [
        {
          id: 1,
          name: "John Doe",
          message: "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
          image:
            "data:image/png;base64,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",
        },
        {
          id: 2,
          name: "Jane Smith",
          message:
            "Praesent tincidunt justo sed magna consequat, at pulvinar lorem posuere.",
          image:
            "data:image/png;base64,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",
        },
        // Add more testimonials as needed
      ],
    };
  },
  created() {
    this.fetchTestimonialData();
  },
  methods: {
    async fetchTestimonialData() {
      try {
        const response = await fetch("/api/customer/testimonials"); // Replace '/api/blog' with your actual API endpoint
        const data = await response.json();
        this.testimonials = data;
      } catch (error) {
        console.error("Error fetching blog data:", error);
      }
    },
  },
};
</script>

<style scoped>
.testimonials {
  display: flex;
  flex-wrap: wrap;
}

.card {
  width: 300px;
  margin: 10px;
  padding: 10px;
  border: 1px solid #ccc;
}

.card-image {
  width: 100%;
  height: auto;
}

.card-title {
  margin-top: 0;
}

.card-description {
  margin-bottom: 0;
}
</style>

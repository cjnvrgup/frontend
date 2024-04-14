<template>

  <!-- 
  <div class="hello">
    <button @click="fetchData">Fetch data</button>
    <div v-if="data" id="dataDiv">
      <img :src="data.avatar" alt="avatar">
      <pre>{{ data.first_name + " " + data.last_name }}</pre>
      <p>"{{ data.employment.title }}"</p> 
      {{ data }}
    </div>
  -->
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#">
      <img src=".././assets/logo.png" width="40" height="40" class="d-inline-block align-top" alt="">
    </a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav"
      aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item active">
          <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Transaction</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Master</a>
        </li>
        <li class="nav-item">
          <a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
        </li>
      </ul>
    </div>
  </nav>


  <div class="container">

    <div class="container mt-4">
      <div class="row">
        <div class="col-md-4 mb-3">
          <label for="validationDefault01">Product Id</label>
          <input type="text" class="form-control" id="validationDefault01" placeholder="Product Id"
            v-model="data.productId" required>
        </div>
        <div class="col-md-4 mb-3">
          <label for="validationDefault02">Name</label>
          <input type="text" class="form-control" id="validationDefault02" placeholder="Last name" v-model="data.name"
            required>
        </div>
        <div class="col-md-4 mb-3">
          <label for="validationDefaultUsername">Weight</label>
          <div class="input-group">
            <input type="text" class="form-control" id="validationDefaultUsername" placeholder="Weight"
              v-model="data.weight" aria-describedby="inputGroupPrepend2" required>
          </div>
        </div>
      </div>
      <!-- <div class="row">
        <div class="col-md-6 mb-3">
          <label for="validationDefault03">City</label>
          <input type="text" class="form-control" id="validationDefault03" placeholder="City" required>
        </div>
        <div class="col-md-3 mb-3">
          <label for="validationDefault04">State</label>
          <input type="text" class="form-control" id="validationDefault04" placeholder="State" required>
        </div>
        <div class="col-md-3 mb-3">
          <label for="validationDefault05">Zip</label>
          <input type="text" class="form-control" id="validationDefault05" placeholder="Zip" required>
        </div>
      </div> -->
    </div>


    <nav class="mt-4">
      <div class="nav nav-pills" id="nav-tab" role="tablist">
        <button class="nav-link active pl-2" id="nav-home-tab" data-bs-toggle="tab" data-bs-target="#nav-home"
          type="button" role="tab" aria-controls="nav-home" aria-selected="true">Home</button>
        <button class="nav-link" id="nav-profile-tab" data-bs-toggle="tab" data-bs-target="#nav-profile" type="button"
          role="tab" aria-controls="nav-profile" aria-selected="false">Reviews</button>
        <button class="nav-link" id="nav-contact-tab" data-bs-toggle="tab" data-bs-target="#nav-contact" type="button"
          role="tab" aria-controls="nav-contact" aria-selected="false">Recommendations</button>
      </div>
    </nav>
    <div class="container">

      <div class="tab-content" id="nav-tabContent">
        <div class="tab-pane fade show active mt-3" id="nav-home" role="tabpanel" aria-labelledby="nav-home-tab">
          <div class="container">
            <form>
              <div class="row">
                <div class="form-group col-md-6">
                  <label for="inputEmail4">Email</label>
                  <input type="email" class="form-control" id="inputEmail4" placeholder="Email">
                </div>
                <div class="form-group col-md-6">
                  <label for="inputPassword4">Password</label>
                  <input type="password" class="form-control" id="inputPassword4" placeholder="Password">
                </div>
              </div>
              <div class="form-group">
                <label for="inputAddress">Address</label>
                <input type="text" class="form-control" id="inputAddress" placeholder="1234 Main St">
              </div>
              <div class="form-group">
                <label for="inputAddress2">Address 2</label>
                <input type="text" class="form-control" id="inputAddress2" placeholder="Apartment, studio, or floor">
              </div>
              <div class="row">
                <div class="form-group col-md-6">
                  <label for="inputCity">City</label>
                  <input type="text" class="form-control" id="inputCity">
                </div>
                <div class="form-group col-md-4">
                  <label for="inputState">State</label>
                  <select id="inputState" class="form-control">
                    <option selected>Choose...</option>
                    <option>...</option>
                  </select>
                </div>
                <div class="form-group col-md-2">
                  <label for="inputZip">Zip</label>
                  <input type="text" class="form-control" id="inputZip">
                </div>
              </div>
              <div class="form-group">
                <div class="form-check">
                  <input class="form-check-input" type="checkbox" id="gridCheck">
                  <label class="form-check-label" for="gridCheck">
                    Check me out
                  </label>
                </div>
              </div>
              <button type="submit" class="btn btn-primary">Sign in</button>
            </form>
          </div>
        </div>
        <div class="tab-pane fade" id="nav-profile" role="tabpanel" aria-labelledby="nav-profile-tab">
          <table class="table table-striped">
            <thead>
              <tr>
                <th scope="col">Review Id</th>
                <th scope="col">Author</th>
                <th scope="col">Subject</th>
                <th scope="col">Content</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="review in reviews" :key="review">
                <th scope="row">{{ review.reviewId }}</th>
                <td>{{ review.author }}</td>
                <td>{{ review.subject }}</td>
                <td>{{ review.content }}</td>
              </tr>
            </tbody>
          </table>
        </div>
        <div class="tab-pane fade" id="nav-contact" role="tabpanel" aria-labelledby="nav-contact-tab">
          <table class="table table-striped">
            <thead>
              <tr>
                <th scope="col">Recommendation Id</th>
                <th scope="col">Author</th>
                <th scope="col">Rate</th>
                <th scope="col">Content</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="recommendation in recommendations" :key="recommendation">
                <th scope="row">{{ recommendation.recommendationId }}</th>
                <td>{{ recommendation.author }}</td>
                <td>{{ recommendation.rate }}</td>
                <td>{{ recommendation.content }}</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      data: null,
      recommendations: null,
      reviews: null,
    };
  },
  methods: {
    async fetchData() {
      // const response = await fetch("https://random-data-api.com/api/v2/users"); 
      const response = await fetch("http://localhost:8080/product-composite/1");
      this.data = await response.json();
      this.recommendations = this.data.recommendations;
      this.reviews = this.data.reviews;
    },
  },
  beforeMount() {
    this.fetchData()
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>

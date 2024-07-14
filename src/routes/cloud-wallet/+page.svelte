<script lang="ts">
  /** @type {import('./$types').ActionData} */
  export let form;
</script>

<style>
  .form-container {
    max-width: 600px;
    margin: 0 auto;
    padding: 2rem;
    border-radius: 0.5rem;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    background-color: #333; /* Dark background */
    color: #fff; /* White text */
  }

  .form-title {
    font-size: 1.5rem;
    font-weight: bold;
    margin-bottom: 1rem;
    color: #fff; /* White text */
  }

  .form-field {
    margin-bottom: 1rem;
  }

  .form-label {
    display: block;
    font-size: 0.875rem;
    font-weight: bold;
    margin-bottom: 0.5rem;
    color: #ccc; /* Light gray text */
  }

  .form-input {
    width: 100%;
    padding: 0.75rem;
    border: 1px solid #555; /* Darker border */
    border-radius: 0.25rem;
    font-size: 1rem;
    color: #fff; /* White text */
    background-color: #444; /* Darker input background */
  }

  .form-button {
    display: block;
    width: 100%;
    padding: 0.75rem;
    background-color: #007bff;
    color: #ffffff;
    font-size: 1rem;
    font-weight: bold;
    border: none;
    border-radius: 0.25rem;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }

  .form-button:hover {
    background-color: #0056b3;
  }

  .form-message {
    margin-top: 1rem;
    font-size: 1rem;
    color: #28a745;
  }

  .form-error {
    margin-top: 1rem;
    font-size: 1rem;
    color: #dc3545;
  }
</style>

<div class="form-container">
  <h2 class="form-title">Login</h2>
  <form method="POST" action="?/login">
    <div class="form-field">
      <label class="form-label" for="email">Email</label>
      <input class="form-input" id="email" type="email" name="email" placeholder="Enter email" />
    </div>
    <div class="form-field">
      <label class="form-label" for="password">Password</label>
      <input class="form-input" id="password" type="password" name="password" placeholder="Enter password" />
    </div>
    <button type="submit" class="form-button">Log In</button>
  </form>
  {#if form?.success}
    <p class="form-message">Logged In. Your balance is {form.balance}!</p>
  {/if}
  {#if form?.error}
    <p class="form-error">Error: {form.error}</p>
  {/if}
</div>

<div class="form-container mt-10">
  <h2 class="form-title">Pay</h2>
  <form method="POST" action="?/pay">
    <div class="form-field">
      <label class="form-label" for="email">Email</label>
      <input class="form-input" id="email" type="email" name="email" placeholder="Enter email" />
    </div>
    <div class="form-field">
      <label class="form-label" for="password">Password</label>
      <input class="form-input" id="password" type="password" name="password" placeholder="Enter password" />
    </div>
    <div class="form-field">
      <label class="form-label" for="paymail">Paymail</label>
      <input class="form-input" id="paymail" type="text" name="paymail" placeholder="Enter paymail" />
    </div>
    <div class="form-field">
      <label class="form-label" for="amount">Amount</label>
      <input class="form-input" id="amount" type="number" name="amount" placeholder="Enter amount" />
    </div>
    <button type="submit" class="form-button">Pay</button>
  </form>
  {#if form?.success}
    <p class="form-message">The payment was successful. Here is your <a href="https://whatsonchain.com/tx/{form.payment}" target="_blank">transaction</a>!</p>
  {/if}
  {#if form?.error}
    <p class="form-error">Error: {form.error}</p>
  {/if}
</div>

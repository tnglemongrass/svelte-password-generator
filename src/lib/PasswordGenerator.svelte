<script lang="ts">
  function generatePasswords(length, count) {
    const characters =
      "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";
    const passwords = [];

    for (let i = 0; i < count; i++) {
      let password = "";
      for (let j = 0; j < length; j++) {
        password += characters.charAt(
          Math.floor(Math.random() * characters.length)
        );
      }
      passwords.push(password);
    }

    return passwords;
  }

  let length = 8;
  let count = 100;
  let passwords = generatePasswords(length, count);
</script>

<div class="password-generator-container">
  {#each passwords as password}
    <div class="password">
      {password}
    </div>
  {/each}
</div>

<style>
  .password-generator-container {
    max-width: 800px;
    margin: 40px auto;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
    gap: 10px;
    padding: 20px;
    background-color: #f9f9f9;
    border: 1px solid #ddd;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  }

  .password {
    padding: 10px;
    background-color: #fff;
    border: 1px solid #ddd;
    border-radius: 5px;
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
    text-align: center;
  }
</style>

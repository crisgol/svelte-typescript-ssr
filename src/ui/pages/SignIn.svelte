<svelte:head>
  <title>Sign In</title>
</svelte:head>

<NavBar />

<section class="section">
  <div class="container">
    <div class="columns">
      <div class="column">
        <h1 class="title">Sign In</h1>
        <p class="subtitle is-4">Something <strong>should</strong> be here</p>

        {#if (networkError)}
          <div class="notification is-danger">
            {networkError}
          </div>
        {/if}

        <form>
          <div class="field">
            <label class="label">Username / Email</label>
            <div class="control">
              <input class="input" name="usernameOrEmail" type="text" placeholder="e.g Alex Smith" on:keyup={fillForm} on:change={fillForm} on:focusout={fillForm} />
            </div>
            <p class="help is-danger">{errorsInput.usernameOrEmail}</p>
          </div>
          
          <div class="field">
            <label class="label">Password</label>
            <div class="control">
              <input class="input" name="password" type="password" placeholder="" on:keyup={fillForm} on:change={fillForm} on:focusout={fillForm} />
            </div>
            <p class="help is-danger">{errorsInput.password}</p>
          </div>

          <div class="field is-grouped">
            <div class="control">
              <button class="button is-link" on:click={submitFormHandler} disabled={!canSubmitForm}>Submit</button>
            </div>
            <div class="control">
              <a class="button is-text" type="button" href="/">Cancel</a>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</section>


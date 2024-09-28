# Contact me

Feel free to contact me if I can be of any help. Here are my areas of expertise: Bitcoin, decentralized technologies, intellectual property, startups, sustainable mobility, education.

![Nostr icon](https://raw.githubusercontent.com/mbarulli/nostr-logo/refs/heads/main/PNG/nostr-icon-purple-32x32.png)  
I'm mostly active on Nostr.
- My [Nostr profile on Primal](https://primal.net/p/npub18nagz6a53yh6d05e8trj487dhvyfhh4qchvsz87jqng4g4zl5tvs825evl)   
- My Lightning address: ⚡mbarulli@getalby.com

If you have not yet joined Nostr, you may contact me via [LinkedIn](https://www.linkedin.com/in/mbarulli) or [X](https://www.x.com/mbarulli).
        
<!-- Contact Form from Formspree.io -->
<script>
       window.onbeforeunload = () => {
       for(const form of document.getElementsByTagName('form')) {
       form.reset();
       }
}
</script>

<form class="view"
       action="https://formspree.io/f/xzbqywlr"
       method="POST"
       >
       <label>
       Your email:
            <input type="email" name="email">
          </label><br>
          <label>
            Your message:
            <textarea name="message"></textarea>
          </label><br>
          <button type="submit">Send</button>
        </form>


<!-- modify this form HTML and place wherever you want your form -->
<form id="my-form" action="https://formspree.io/f/xzbqywlr" method="POST">
  <label>Email:</label>
  <input type="email" name="email" />
  <label>Message:</label>
  <input type="text" name="message" />
  <button id="my-form-button">Submit</button>
  <p id="my-form-status"></p>
</form>

<!-- Place this script at the end of the body tag -->
<script>
  var form = document.getElementById("my-form");
  
  async function handleSubmit(event) {
    event.preventDefault();
    var status = document.getElementById("my-form-status");
    var data = new FormData(event.target);
    fetch(event.target.action, {
      method: form.method,
      body: data,
      headers: {
          'Accept': 'application/json'
      }
    }).then(response => {
      if (response.ok) {
        status.innerHTML = "Thanks for your submission!";
        form.reset()
      } else {
        response.json().then(data => {
          if (Object.hasOwn(data, 'errors')) {
            status.innerHTML = data["errors"].map(error => error["message"]).join(", ")
          } else {
            status.innerHTML = "Oops! There was a problem submitting your form"
          }
        })
      }
    }).catch(error => {
      status.innerHTML = "Oops! There was a problem submitting your form"
    });
  }
  form.addEventListener("submit", handleSubmit)
</script>

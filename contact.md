---
layout: single
title: Contact
permalink: /contact/
---

<div id="content" class="bg-white py-6 sm:py-6">
  <div class="mx-auto max-w-3xl px-6 text-left">
    <p class="text-lg text-gray-700">
      Ready to start? Reach out at hello@rootcreative.com to book a discovery call and map the next step.
    </p>

    <p class="text-lg text-gray-700">
      We’d love to hear about what you’re building and where you need the most clarity. Whether you’re launching something new, refining an existing experience, or looking for a fresh perspective, we’re happy to start the conversation.
    </p>

    <p class="mt-4 text-gray-700">
      Tell us a bit about your goals, timeline, and the challenges you’re navigating. We’ll follow up with a thoughtful response and talk through the best next step.
    </p>

    <ul class="mt-6 space-y-2 text-gray-700">
      <li> Product strategy and roadmap support</li>
      <li> Brand and interface design</li>
      <li> Web and product development</li>
    </ul>
  </div>

  <div class="mx-auto mt-10">
    <div class="mx-auto mt-3">
      <form
        id="my-form"
        action="https://formspree.io/f/xwpoeark"
        method="POST"
        >
        <div class="md:flex md:items-center mb-6">
          <div class="md:w-1/3">
            <label class="block text-gray-500 font-bold md:text-right mb-1 md:mb-0 pr-4" for="email">
              Email:
            </label>
          </div>
          <div class="px-10 md:w-2/3">
            <input class="p-2 min-h-10 sm:min-h-5 bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-neutral-500 field-sizing-fixed w-80" id="email" name="email" type="email">
          </div>
        </div>

        <div class="md:flex md:items-center mb-6">
          <div class="md:w-1/3">
            <label class="block text-gray-500 font-bold md:text-right mb-1 md:mb-0 pr-4" for="message">
              Message:
            </label>
          </div>
          <div class="md:w-2/3 px-10 ">
            <textarea class="min-h-80 p-2 sm:min-h-40 bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-neutral-500 field-sizing-fixed w-80" id="message" name="message" type="text"></textarea>
          </div>
        </div>
        <!-- your other form fields go here -->
        <div class="md:flex md:items-center">
          <div class="md:w-1/3"></div>
          <div class="md:w-2/3">
            <button
              class="w-full px-4 py-2 mt-10 font-medium tracking-wide text-white capitalize transition-colors duration-300 transform bg-yellow-500 rounded-md hover:bg-yellow-600 focus:outline-none focus:bg-yellow-600">
              Send
            </button>
            <p id="my-form-status"></p>
          </div>
        </div>
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
    </div>
  </div>
</div>
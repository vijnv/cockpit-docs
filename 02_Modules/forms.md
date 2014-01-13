### Forms

Forms have been always a pain. Especially handling the data after form submission. 
We're happy to say that now Cockpit will do the dirty job for you. Cockpit collects the data + transfers it via email. We choose not to build a form builder, because we think you know HTML very well and we don't want to step in your code flow.

#### Usage

This is a really basic contact form with a name, email and message field.

    <form name="contact">
      <p>
        <label for="name">Name</label>
        <input id="name" name="name"/>
      </p>
      <p>
        <label for="email">Email</label>
        <input id="email" name="email"/>
      </p>
      <p>
        <label for="message">Message</label>
        <textarea id="message" name="message"></textarea>
      </p>
      <p>
        <button type="submit">Send</button>
      </p>
    </form>


To make it work with Cockpit, create a form in the Cockpit backend called **contact**. Then simply replace the &lt;form&gt; tag with the form function and **wrap all fields we want to collect with form[...]**. We also added a success message div to be shown once the form has been successfully submitted:


    <?php form("contact");?>
      <div class="form-message-success">
        Thank You! I'll get back to you real soon...
      </div>

      <p>
        <label for="name">Name</label>
        <input id="name" name="form[name]"/>
      </p>
      <p>
        <label for="email">Email</label>
        <input id="email" name="form[email]"/>
      </p>
      <p>
        <label for="message">Message</label>
        <textarea id="message" name="form[message]"></textarea>
      </p>
      <p>
        <button type="submit">Send</button>
      </p>
    </form>


Done! Happy collecting form data.


<div class="uk-alert uk-alert-warning">
    <strong><i class="uk-icon-exclamation-triangle"></i> Attention</strong>
    <p>
        The forms module depends on jQuery. So please make sure to include jQuery on the page you want to use the form function.
    </p>
</div>

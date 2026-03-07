---
layout: default
title: Contact
permalink: /contact/
---

<section class="page-content">
  <div class="container">
    <h1 class="page-title">Contact Us</h1>

    <div class="contact-grid">
      <div class="contact-info">
        <h3>Get in Touch</h3>
        <p>Have a question or ready to improve your security posture? Reach out and we'll get back to you promptly.</p>

        <h3>Email</h3>
        <a href="mailto:contact@greywingsec.com">contact@greywingsec.com</a>

        <h3>LinkedIn</h3>
        <a href="https://linkedin.com/company/grey-wing-security" target="_blank" rel="noopener">Grey Wing Security on LinkedIn</a>
      </div>

      <div>
        <form class="contact-form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
          <div>
            <label for="name">Name</label>
            <input type="text" id="name" name="name" required>
          </div>
          <div>
            <label for="email">Email</label>
            <input type="email" id="email" name="_replyto" required>
          </div>
          <div>
            <label for="message">Message</label>
            <textarea id="message" name="message" required></textarea>
          </div>
          <button type="submit" class="btn btn-primary">Send Message</button>
        </form>
        <p style="margin-top:0.75rem; font-size:0.85rem; color:var(--text-secondary);">
          Note: To activate this form, replace <code>YOUR_FORM_ID</code> in the page source with your <a href="https://formspree.io" target="_blank">Formspree</a> form ID.
        </p>
      </div>
    </div>
  </div>
</section>

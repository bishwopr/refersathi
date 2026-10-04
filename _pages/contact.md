---
title: "Contact"
layout: page
permalink: "/contact.html"
---

<div class="rs-contact-wrap" id="rs-contact-wrap">
  <div class="rs-flying-unit" id="rs-flying-unit">

    <!-- 🕊️ Pigeon sits ABOVE the envelope, inside the same unit -->
    <div class="rs-pigeon">🕊️</div>

    <!-- Envelope -->
    <div class="rs-envelope" id="rs-envelope">

      <!-- Flap -->
      <div class="rs-envelope-flap"></div>

      <!-- Body with form -->
      <div class="rs-envelope-body">
        <h2 class="rs-envelope-title">Send us a letter</h2>
        <p class="rs-envelope-sub">Drop us a message — our pigeon will deliver it.</p>

        <form id="rs-contact-form" action="https://formspree.io/f/xbglnnlj" method="POST">
          <div class="row">
            <div class="col-md-6 mb-3">
              <input class="form-control rs-envelope-input" type="text" name="name" placeholder="Name*" required>
            </div>
            <div class="col-md-6 mb-3">
              <input class="form-control rs-envelope-input" type="email" name="_replyto" placeholder="E-mail Address*" required>
            </div>
          </div>
          <textarea rows="6" class="form-control rs-envelope-input mb-3" name="message" placeholder="Your message*" required></textarea>
          <button type="submit" class="rs-envelope-send">
            <i class="fa fa-paper-plane"></i> Send Letter
          </button>
        </form>
      </div>

      <!-- Wax seal -->
      <div class="rs-envelope-seal">✉</div>
    </div>

  </div>
</div>

<!-- Sent confirmation dialogue -->
<div id="rs-sent-dialogue" class="rs-sent-dialogue" aria-hidden="true">
  <div class="rs-sent-box">
    <div class="rs-sent-icon">✉️</div>
    <h3 class="rs-sent-title">Message Sent!</h3>
    <p class="rs-sent-sub">Our pigeon is flying it over now.</p>
    <div class="rs-sent-bar"><div class="rs-sent-bar-fill"></div></div>
  </div>
</div>

<!-- ✅ Delivered confirmation — appears after pigeon flies away -->
<div id="rs-delivered" class="rs-delivered" aria-hidden="true">
  <div class="rs-delivered-box">
    <div class="rs-delivered-icon">✅</div>
    <h3 class="rs-delivered-title">Delivered!</h3>
    <p class="rs-delivered-sub">Your letter has safely reached ReferSathi.<br>We'll get back to you shortly.</p>
    <div class="rs-delivered-redirect">Returning home…</div>
    <div class="rs-delivered-bar"><div class="rs-delivered-bar-fill"></div></div>
  </div>
</div>

<style>
/* ============================================
   REFERSATHI — Contact Page as Envelope
   ============================================ */

.rs-contact-wrap {
    display: flex;
    justify-content: center;
    padding: 140px 20px 100px;
    background: linear-gradient(180deg, #f7f8fa 0%, #eef3f1 100%);
    min-height: 70vh;
    position: relative;
}

/* FLYING UNIT */
.rs-flying-unit {
    position: relative;
    width: 100%;
    max-width: 720px;
    transform-origin: center center;
    transition: transform 1.6s cubic-bezier(0.5, -0.3, 0.4, 1.4),
                opacity 1.6s ease 0.6s;
}

.rs-contact-wrap.rs-fly .rs-flying-unit {
    transform: translate(70vw, -70vh) rotate(28deg) scale(0.35);
    opacity: 0;
}

/* PIGEON */
.rs-pigeon {
    position: absolute;
    top: -80px;
    left: 50%;
    transform: translateX(-50%) scaleX(-1) translateY(-30px);
    font-size: 96px;
    line-height: 1;
    opacity: 0;
    pointer-events: none;
    z-index: 10;
    filter: drop-shadow(0 8px 16px rgba(0, 0, 0, 0.28));
    transition: opacity 0.4s ease,
                transform 0.7s cubic-bezier(0.3, -0.3, 0.4, 1.5);
}

.rs-contact-wrap.rs-fly .rs-pigeon {
    opacity: 1;
    transform: translateX(-50%) scaleX(-1) translateY(0);
    animation: rsPigeonFlap 0.4s ease-in-out infinite alternate 0.6s;
}

@keyframes rsPigeonFlap {
    from { transform: translateX(-50%) scaleX(-1) translateY(0) rotate(0deg); }
    to   { transform: translateX(-50%) scaleX(-1) translateY(-8px) rotate(-3deg); }
}

/* ENVELOPE */
.rs-envelope {
    position: relative;
    width: 100%;
    background: #f4efe4;
    border-radius: 6px;
    box-shadow:
        0 20px 60px rgba(0, 0, 0, 0.18),
        0 6px 20px rgba(0, 0, 0, 0.10);
    padding-top: 90px;
    border: 1px solid #e4dcc8;
}

.rs-envelope-flap {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    height: 90px;
    background: linear-gradient(135deg, #efe7d3 0%, #e6dcc4 100%);
    clip-path: polygon(0 0, 100% 0, 50% 100%);
    box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.06);
    z-index: 3;
    transform-origin: top center;
    transition: transform 0.6s ease;
}

.rs-contact-wrap.rs-fly .rs-envelope-flap {
    transform: rotateX(180deg);
}

.rs-envelope-body {
    position: relative;
    background: #fbf8f0;
    padding: 40px 44px 44px;
    z-index: 2;
    border-top: 1px solid #e4dcc8;
    transition: opacity 0.6s ease;
}

.rs-contact-wrap.rs-fly .rs-envelope-body {
    opacity: 0.3;
}

.rs-envelope-title {
    font-size: 1.75rem;
    font-weight: 800;
    color: #1f1f1f;
    margin: 0 0 4px;
    letter-spacing: -0.5px;
}

.rs-envelope-sub {
    font-size: 0.95rem;
    color: #6b6b6b;
    margin: 0 0 24px;
}

.rs-envelope-input {
    background: #ffffff !important;
    border: 1px solid #e2dcc8 !important;
    border-radius: 8px !important;
    padding: 12px 16px !important;
    font-size: 15px !important;
    color: #1f1f1f !important;
    transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.rs-envelope-input:focus {
    border-color: #11998e !important;
    box-shadow: 0 0 0 3px rgba(17, 153, 142, 0.12) !important;
    outline: none !important;
}

.rs-envelope-send {
    width: 100%;
    background: linear-gradient(135deg, #11998e, #38ef7d);
    color: #ffffff;
    border: none;
    border-radius: 10px;
    padding: 14px 20px;
    font-size: 1rem;
    font-weight: 800;
    letter-spacing: 0.3px;
    cursor: pointer;
    box-shadow: 0 6px 18px rgba(17, 153, 142, 0.28);
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.rs-envelope-send:hover {
    transform: translateY(-2px);
    box-shadow: 0 10px 24px rgba(17, 153, 142, 0.35);
}

.rs-envelope-send i {
    margin-right: 8px;
    transition: transform 0.3s ease;
}

.rs-envelope-send:hover i {
    transform: translate(6px, -6px) rotate(15deg);
}

.rs-envelope-seal {
    position: absolute;
    bottom: -18px;
    right: 30px;
    width: 56px;
    height: 56px;
    border-radius: 50%;
    background: radial-gradient(circle at 30% 30%, #d94f4f, #a01d1d);
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 1.5rem;
    box-shadow:
        0 6px 14px rgba(160, 29, 29, 0.4),
        inset 0 -3px 6px rgba(0, 0, 0, 0.2),
        inset 0 3px 6px rgba(255, 255, 255, 0.15);
    z-index: 4;
    transform: rotate(-8deg);
}

/* ============================================
   SENT DIALOGUE
   ============================================ */
.rs-sent-dialogue {
    position: fixed;
    inset: 0;
    background: rgba(0, 0, 0, 0.45);
    backdrop-filter: blur(4px);
    -webkit-backdrop-filter: blur(4px);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 10001;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.3s ease;
    padding: 20px;
}

.rs-sent-dialogue.rs-sent-show {
    opacity: 1;
    pointer-events: auto;
}

.rs-sent-box {
    background: #ffffff;
    border-radius: 20px;
    padding: 32px 36px 28px;
    text-align: center;
    max-width: 380px;
    width: 100%;
    box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
    transform: scale(0.9);
    transition: transform 0.35s cubic-bezier(0.2, 0.9, 0.3, 1.3);
}

.rs-sent-dialogue.rs-sent-show .rs-sent-box {
    transform: scale(1);
}

.rs-sent-icon {
    font-size: 3rem;
    line-height: 1;
    margin-bottom: 12px;
    animation: rsSentPop 0.6s cubic-bezier(0.2, 0.9, 0.3, 1.3);
}

@keyframes rsSentPop {
    0%   { transform: scale(0) rotate(-45deg); }
    60%  { transform: scale(1.2) rotate(10deg); }
    100% { transform: scale(1) rotate(0deg); }
}

.rs-sent-title {
    font-size: 1.5rem;
    font-weight: 800;
    color: #0f4d3a;
    margin: 0 0 6px;
    letter-spacing: -0.5px;
}

.rs-sent-sub {
    font-size: 0.95rem;
    color: #6b6b6b;
    margin: 0 0 20px;
}

.rs-sent-bar {
    width: 100%;
    height: 5px;
    background: #e8f5ef;
    border-radius: 4px;
    overflow: hidden;
}

.rs-sent-bar-fill {
    width: 0;
    height: 100%;
    background: linear-gradient(90deg, #11998e, #38ef7d);
    border-radius: 4px;
    animation: rsSentProgress 2.4s linear forwards;
}

@keyframes rsSentProgress {
    from { width: 0; }
    to   { width: 100%; }
}

/* ============================================
   DELIVERED CONFIRMATION
   ============================================ */
.rs-delivered {
    position: fixed;
    inset: 0;
    background: rgba(0, 0, 0, 0.5);
    backdrop-filter: blur(6px);
    -webkit-backdrop-filter: blur(6px);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 10003;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.4s ease;
    padding: 20px;
}

.rs-delivered.rs-delivered-show {
    opacity: 1;
    pointer-events: auto;
}

.rs-delivered-box {
    background: #ffffff;
    border-radius: 24px;
    padding: 40px 40px 32px;
    text-align: center;
    max-width: 420px;
    width: 100%;
    box-shadow: 0 24px 80px rgba(0, 0, 0, 0.35);
    transform: scale(0.85);
    transition: transform 0.45s cubic-bezier(0.2, 0.9, 0.3, 1.4);
    border: 2px solid #e8f5ef;
}

.rs-delivered.rs-delivered-show .rs-delivered-box {
    transform: scale(1);
}

.rs-delivered-icon {
    font-size: 4rem;
    line-height: 1;
    margin-bottom: 16px;
    display: inline-block;
    animation: rsDeliveredPop 0.7s cubic-bezier(0.2, 0.9, 0.3, 1.5);
}

@keyframes rsDeliveredPop {
    0%   { transform: scale(0) rotate(-90deg); }
    50%  { transform: scale(1.3) rotate(15deg); }
    100% { transform: scale(1) rotate(0deg); }
}

.rs-delivered-title {
    font-size: 1.9rem;
    font-weight: 800;
    color: #0f4d3a;
    margin: 0 0 8px;
    letter-spacing: -0.5px;
}

.rs-delivered-sub {
    font-size: 0.95rem;
    color: #6b6b6b;
    margin: 0 0 22px;
    line-height: 1.5;
}

.rs-delivered-redirect {
    font-size: 0.85rem;
    color: #11998e;
    font-weight: 700;
    letter-spacing: 0.5px;
    text-transform: uppercase;
    margin-bottom: 10px;
}

.rs-delivered-bar {
    width: 100%;
    height: 4px;
    background: #e8f5ef;
    border-radius: 3px;
    overflow: hidden;
}

.rs-delivered-bar-fill {
    width: 0;
    height: 100%;
    background: linear-gradient(90deg, #11998e, #38ef7d);
    border-radius: 3px;
    animation: rsDeliveredProgress 2.2s linear forwards;
}

@keyframes rsDeliveredProgress {
    from { width: 0; }
    to   { width: 100%; }
}

/* ============================================
   MOBILE
   ============================================ */
@media (max-width: 576px) {
    .rs-contact-wrap { padding: 120px 20px 80px; }
    .rs-pigeon { font-size: 68px; top: -60px; }
    .rs-envelope-body { padding: 28px 22px 32px; }
    .rs-envelope-title { font-size: 1.4rem; }
    .rs-envelope-seal { width: 46px; height: 46px; font-size: 1.2rem; right: 18px; }
    .rs-sent-box { padding: 26px 24px 22px; }
    .rs-sent-title { font-size: 1.25rem; }
    .rs-sent-icon { font-size: 2.5rem; }
    .rs-delivered-box { padding: 30px 26px 26px; }
    .rs-delivered-title { font-size: 1.5rem; }
    .rs-delivered-icon { font-size: 3rem; }
}
</style>

<script>
(function() {
    var form = document.getElementById('rs-contact-form');
    if (!form) return;

    form.addEventListener('submit', function(e) {
        e.preventDefault();

        var wrapper   = document.getElementById('rs-contact-wrap');
        var dialogue  = document.getElementById('rs-sent-dialogue');
        var delivered = document.getElementById('rs-delivered');

        // 1. Show "Message Sent!" dialogue
        dialogue.classList.add('rs-sent-show');
        dialogue.setAttribute('aria-hidden', 'false');

        setTimeout(function() {
            var icon = document.querySelector('.rs-sent-icon');
            if (icon) icon.textContent = '✅';
        }, 900);

        // 2. Submit to Formspree (skip in test mode)
        if (!window.RS_TEST_MODE) {
            fetch(form.action, {
                method: 'POST',
                body: new FormData(form),
                headers: { 'Accept': 'application/json' }
            }).catch(function() {});
        } else {
            console.log('🧪 TEST MODE: form submission skipped.');
        }

        // 3. After dialogue, dismiss + launch the pigeon flight
        setTimeout(function() {
            dialogue.classList.remove('rs-sent-show');
            dialogue.setAttribute('aria-hidden', 'true');
            wrapper.classList.add('rs-fly');
        }, 2400);

        // 4. After pigeon finishes flying away, show "Delivered!"
        setTimeout(function() {
            delivered.classList.add('rs-delivered-show');
            delivered.setAttribute('aria-hidden', 'false');
        }, 4400);   // pigeon flight takes ~1.6s + fade, so 4.4s from start

        // 5. Redirect home after "Delivered!" shows for 2.2s
        if (!window.RS_TEST_MODE) {
            setTimeout(function() {
                window.location.href = '{{ site.baseurl }}/index.html';
            }, 6600);
        } else {
            setTimeout(function() {
                console.log('🧪 TEST MODE: redirect skipped. Run window.rsReset(); to replay.');
            }, 6600);
        }
    });

    // Reset helper for testing
    window.rsReset = function() {
        document.getElementById('rs-contact-wrap').classList.remove('rs-fly');
        var d  = document.getElementById('rs-sent-dialogue');
        var de = document.getElementById('rs-delivered');
        d.classList.remove('rs-sent-show');
        d.setAttribute('aria-hidden', 'true');
        de.classList.remove('rs-delivered-show');
        de.setAttribute('aria-hidden', 'true');
        var icon = document.querySelector('.rs-sent-icon');
        if (icon) icon.textContent = '✉️';
        form.reset();
        console.log('🔄 Reset. Fill the form to replay.');
    };
})();
</script>

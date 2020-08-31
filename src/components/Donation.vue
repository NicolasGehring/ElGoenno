<template>
  <section class="bg-light" id="team">
    <div class="container">
      <div class="row">
        <div class="col-lg-12 text-center">
          <h2 class="section-heading text-uppercase">Unterstütze uns</h2>
          <h3 class="section-subheading text-muted">
            <b>50% der Spenden werden von uns an einen wohltätigen Zweck gespendet!</b>
            <br />Wenn dir die Gönnerwoche gefallen hat würden wir uns sehr über eine Spende freuen. Bei einer Spende von 10€ trinken Simon und ich einen Shot und senden dir ein persönliches Video mit Dankesnachricht. Alternativ nehmen wir Spenden in Form von Bargeld oder Naturalien an.
          </h3>
        </div>
      </div>
    </div>
    <form action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_top">
      <input type="hidden" name="cmd" value="_s-xclick" />
      <input type="hidden" name="hosted_button_id" value="F9376G3HKUB82" />
      <input
        type="image"
        src="https://www.paypalobjects.com/en_US/DK/i/btn/btn_donateCC_LG.gif"
        border="0"
        name="submit"
        title="PayPal - The safer, easier way to pay online!"
        alt="Donate with PayPal button"
      />
      <img alt border="0" src="https://www.paypal.com/en_DE/i/scr/pixel.gif" width="1" height="1" />
    </form>
  </section>
</template>

---
title: "Contact"
permalink: "/contact"
---

<form  action="https://formsubmit.co/jujaraynaveen@gmail.com" method="POST">    
<p class="mb-4">Please send your message to {{site.name}}. We will reply as soon as possible!</p>
<div class="form-group row">
<div class="col-md-6">
<input class="form-control" type="text" name="name" placeholder="Name" required>
</div>
<div class="col-md-6">
<input class="form-control" type="email" name="email" placeholder="E-mail Address" required>
</div>
</div>
<textarea rows="8" class="form-control mb-3" name="message" placeholder="Message" required></textarea>    
<input class="btn btn-success" type="submit" value="Send">
<input type="hidden" name="_captcha" value="false">
</form>
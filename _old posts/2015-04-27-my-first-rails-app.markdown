---
layout:     post
title:      "My first Rails app"
subtitle:   "Get started right away and don't overthink it."
date:       2015-04-27 12:00:00
author:     "Jonathan Mathews"
header-img: "img/post-bg-02.jpg"
comments: 	true
---

<h2 class="section-heading">Background</h2>

<p>At the beginnning of last year, I finally decided to put some of the web development skills I'd been learning to use by finding some of my own things to build. I've heard this advice many times now, and it took me a long time to act on it, but I'd recommend: (1) finding a real project to hone your skills; (2) not worrying about it being a viable business idea (or you'll never get started); (3) writing it up. Trust me, you will learn a lot.</p>

<p>A friend was in the same boat so we embarked on this project together and it made the whole process a lot more interesting and fun. He also taught me a lot, as we both had different ways of thinking about the same problem.</p>

<p>We wanted to focus our first idea on restaurants, despite the fact that they can be expensive customers to acquire. We weren't too concerned about that. As I mentioned earlier, it’s more important just to get started than try and find the perfect business idea, otherwise you'll never start anything. I wish I'd been better at following that advice.</p>

<h2 class="section-heading">The Idea</h2>

<p>We gave ourselves two days to do some customer development, pounding the pavement and talking to bar and restaurant managers. We’d gone in with an initial problem hypothesis and an idea for a solution.</p>

<p>We were focused on the “non-trendy” suburban mid-market segment. I don’t think this is a standard definition in the restaurant industry, but essentially we were avoiding the low budget touristy restaurants, large chains, high end restaurants, and hip &amp; trendy restaurants. Our target customers had probably tried using the likes of GroupOn before, but found that these platforms were not attracting the right customers (bargain hunters instead of customers with long-term value potential).</p>

<p>We wanted to give restaurant owners a chance to attract new regular customers, by incentivising word-of-mouth marketing. We'd do this by offering a platform for reciprocal offers, already used successfully by many online businesses. The restaurant loyalty app space is already crowded, but we believed there was too much friction involved in downloading an app for a single restaurant. Instead, we planned to make the user interface something with which customers were already very familiar: text messages.</p>

<h2 class="section-heading">Getting out of the building</h2>

<p>After speaking to around 15-20 customers, we found that restaurateurs (in our target segment) were certainly thinking about attracting potential longer-term customers, as opposed to the bargain hunters. Talking to customers also helped us to refine the target segment for early adopters and to understand workflows. We also talked to salons and other types of businesses, but found they already had adequate solutions to this problem.</p>

<p>We found that there was one other issue that restaurateurs were thinking about: the rogue negative review on Trip Advisor, Yelp or Time Out. Managers wanted to give customers an opportunity to resolve the issue before they post their review on one of these sites. This is especially relevant in Europe, where customers rarely complain in person. We found that some restaurants would incentivise their staff to collect review cards at the end of meals. Customers are also incentivised to complete these with a monthly prize draw (in exchange for an email address).</p>

<h2 class="section-heading">Designing the MVP</h2>

<p>We started by wondering how we would break the ice with the customer, inviting them to participate in our text message interaction. Asking for feedback gave us the opportunity to do just that. We would request a numeric score just after the customer had left the restaurant.</p>

<p>Once the customer has texted their score, we would ask for additional comments based on the score (e.g. if the score was very low, we would move to a more personal interaction to find out what went wrong). We would then follow up with an offer to forward to a friend via sms or email (and potentially other social channels), where the offer would be activated once the friend had used theirs.</p>

<p>The restaurant would have access to a dashboard, showing response rates, referral rates, redemption rates and nps ratings by day, server, etc. The restaurant would also have various configuration options, such as setting up offers and the ability to send a text to a duty manager if the score was very low.</p>

<p>The interface with the customer would be entirely through SMS, although there would be an HTML landing page showing details of the offer and generating a referral SMS, containing a tracking url.</p>

<div>
<a href="{{ site.baseurl }}/img/first-rails-app-image06.jpg"><img src="{{ site.baseurl }}/img/first-rails-app-image06.jpg" alt="Mapping the workflow"></a>
	<span class="caption text-muted">Figuring out the user flow with Post-its</span>
</div>

<h2 class="section-heading">Getting it built</h2>

<p>We decided we were going to give ourselves three days to build the first prototype, with the goal of ending up with something we could demonstrate to restaurant managers, rather than something that could be used by customers. So, it was more of an “Alpha”, than a “Beta”.</p>
<p>We used <a href="https://www.twilio.com/" target="_blank">Twilio</a> to do all the SMS magic and I was impressed with how incredibly easy it was to use, and quick to learn. Twilio also has a nice Ruby gem that made it incredibly straightforward to integrate into our Rails app. The latency was incredibly low, and in most cases, SMSs were arriving within a few seconds of us issuing the request.</p>
<p>We broke the project down into user stories and entered them into <a href="https://trello.com/" target="_blank">Trello</a>. I’d never used Trello to manage development before, but it worked incredibly well, keeping us on track and focused. It was far more straightforward to use than JIRA, but probably doesn’t scale to large development teams and lacks a lot of the features you need for that.</p>
<p>After three days, we had a prototype that was ready to demonstrate. We deployed it to Heroku and decided to call it Wildfire: the first name that came to mind.</p>

<h2 class="section-heading">Prototype screenshots &amp; flow</h2>
<p></p>
<div class="container-fluid">
	<div class="row">
		<div class="col-md-4">
			<a href="{{ site.baseurl }}/img/first-rails-app-image02.png"><img src="{{ site.baseurl }}/img/first-rails-app-image02.png" alt=""></a>
			<p></p>
			<a href="{{ site.baseurl }}/img/first-rails-app-image01.png"><img src="{{ site.baseurl }}/img/first-rails-app-image01.png" alt=""></a>
			<span class="caption text-muted">Two options for initiating the interaction with the customer. Either the customer initiates with a text to a short code, or the restaurant sends a text to the customer after leaving the restaurant.<br></span>
		</div>
		<div class="col-md-4">
			<a href="{{ site.baseurl }}/img/first-rails-app-image09.png"><img src="{{ site.baseurl }}/img/first-rails-app-image09.png" alt=""></a>
			<span class="caption text-muted">The mobile-optimised landing page. Clicking on the button generates an sms containing the referral link.<br></span>
		</div>
		<div class="col-md-4">
			<a href="{{ site.baseurl }}/img/first-rails-app-image05.png"><img src="{{ site.baseurl }}/img/first-rails-app-image05.png" alt=""></a>
			<span class="caption text-muted">The customer can customize the text and forward to a friend.<br></span>
		</div>
	</div>
</div>
<p></p>
<div class="container-fluid">
	<div class="row">
		<div class="col-md-4">
			<a href="{{ site.baseurl }}/img/first-rails-app-image07.png"><img src="{{ site.baseurl }}/img/first-rails-app-image07.png" alt=""></a>
			<span class="caption text-muted">The friend clicks on the link in the SMS and enters their phone number to receive an SMS with the activation code.<br></span>
		</div>
		<div class="col-md-4">
			<a href="{{ site.baseurl }}/img/first-rails-app-image10.png"><img src="{{ site.baseurl }}/img/first-rails-app-image10.png" alt=""></a>
			<span class="caption text-muted">The friend’s SMS with the activation code. A similar SMS is sent to the referrer when the friend redeems this code.<br></span>
		</div>
		<div class="col-md-4">
			<a href="{{ site.baseurl }}/img/first-rails-app-image00.png"><img src="{{ site.baseurl }}/img/first-rails-app-image00.png" alt=""></a>
			<span class="caption text-muted">Restaurant console: This screen shows a timeline of the customers’ interactions and referral activity.<br></span>
		</div>
	</div>
</div>
<p></p>
<div class="container-fluid">
	<div class="row">
		<div class="col-md-4">
			<a href="{{ site.baseurl }}/img/first-rails-app-image08.png"><img src="{{ site.baseurl }}/img/first-rails-app-image08.png" alt=""></a>
			<span class="caption text-muted">Restaurant console: This screen initiates a text flow to the customer.<br></span>
		</div>
		<div class="col-md-4">
			<a href="{{ site.baseurl }}/img/first-rails-app-image04.png"><img src="{{ site.baseurl }}/img/first-rails-app-image04.png" alt=""></a>
			<span class="caption text-muted">Restaurant console: This screen is used to redeem the offer and triggers the reciprocal reward (if applicable).<br></span>
		</div>
		<div class="col-md-4">
			<a href="{{ site.baseurl }}/img/first-rails-app-image03.png"><img src="{{ site.baseurl }}/img/first-rails-app-image03.png" alt=""></a>
			<span class="caption text-muted">Restaurant console: Settings for the Twilio API and phone numbers - obviously the restaurant would not see this in the real world. (PS: these are not the real ones).<br></span>
		</div>
	</div>
</div>

<h2 class="section-heading">Marketing &amp; Go To Market</h2>

<p>Although we never put this into practice, we did spend some time thinking how we were going to market the product. We wanted to make it very easy for prospects arriving on the landing page to test drive it immediately, using their own mobile phones. In the world of B2B software marketing, you remove a lot of friction if the prospect can see the product in action within a minute or two. “Requesting a demo” via a contact form is far from ideal, and it costs you more time too. A completely automated demo process is the holy grail. Also, it’s a great excuse to collect contact details.</p>
<p>Our plan was to have the user enter their phone number, or email address. They would receive a text asking them to rate a fictitious restaurant. Another text would then follow (depending on their response), thanking them and asking them for more feedback and/or to refer a friend. At this point, they could see their feedback appear live on their screen, with some tooltips explaining what’s going on.</p>
<p>In the background, we can be doing some data gathering to generate a lead score, and either decide to drop them into an email nurturing campaign, or follow up immediately with a sales call.</p>
<p>Pricing? We hadn’t given this much thought, but we talked about 3-4 pricing tiers, with the first being free (possibly), or a one month trial period. Premium tiers would enable more marketing features (such as the ability to configure marketing campaigns for special events/promotions, or get more sophisticated with referral bonuses, e.g. increasing it as a customer refers more friends).</p>
<p>The restaurant owner should be able to test this out on a small scale with very little setup/admin effort on their part. The perfect “happy path” playbook would be: owner does self-service demo on his own phone after finding the landing page; decides to test it out in one restaurant on a few tables using the free tier; spends 10-15 minutes configuring, testing and training; successfully tests; and then decides to roll out across his restaurant, upgrading to a higher tier. Throughout the process, we would run a content marketing program (via email), with tips on how to improve customer service and boost loyalty and engagement, perhaps including interviews with other restaurateurs and users of the product.</p>

<h2 class="section-heading">What happened next</h2>

<p>After demonstrating the prototype to some of the restaurant managers we'd talked to during our customer development exercise, we received some enthusiastic feedback and ideas for some improvements to the product.</p>

<p>We decided not to take the project to the next stage as neither of us were that excited about selling to the restaurant sector, after spending quite a bit of time observing the mechanics of how a restaurant works, and the challenges we'd face in driving adoption.</p>

<p>This was an incredibly worthwhile project and taught me a lot about customer development, being ruthless and creative in simplifying features (it's so easy to come up with ideas and anyone can do that), and getting a prototype built very quickly. Rails is really amazing for that!</p>

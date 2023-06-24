---
title: Kavita+
media_order: 'Activate License.PNG,User-Reviews.PNG,individual-review.PNG,recommendations.PNG,external-reviews.PNG,edit-scrobbling.PNG,scrobbling-set.PNG'
---

Kavita+ is a premium service offered by the Kavita Team which unlocks a set of features for your Kavita application. Kavita+ is a way to gain some monetary support to further dedicate time into the Kavita application, think of it as a way to support the development of Kavita while also getting some sweet features out of it. The goal is to not lock all features behind Kavita+, but add features that otherwise aren't feasible in the base product.

Kavita+ is a monthly subscription for your individual instance and is node-locked. Once active, all users on your server gain the benefit.

**Current Features:**
- External Reviews
- Recommendations
- External Series for Admins
- Remove Donate Link
- Scrobbling Support for AniList
- External Ratings

**Planned:**
- Webhook Support
- Kobo Progress Sync
- Your ideas (you can submit your ideas on Feathub)

## How to Buy
Navigate to Admin Dashboard -> Kavita+ tab. From there, you can purchase a license via the Buy button. A new tab will open prompting you for your pay information. Kavita+ uses Stripe to handling payments. Kavita team does not have any access to your personal information. Please ensure you use a real email, otherwise you will not be able to receive your product key. Upon finishing subscription, you will receive an email from Kavita with your license key. Move to the Activate step.

## How to Activate
From the Admin Dashboard -> Kavita+ tab, press Activate button. This will prompt you for the email you used with Stripe and the License you received via the email. Enter the details and hit save. This will register your Kavita instance with Kavita+ and should reflect instantly. If you ever need to manage your subscription, like cancel it, you can do so via the Manage button. All management is locked around your email. If forever reason your license is showing invalid, use the Check button to re-validate the license.
![Activate%20License](Activate%20License.PNG "Activate%20License")

### External Reviews
Kavita+ offers external reviews on the Series Detail page. These reviews are aggregated from multiple sources and sorted. If users on your server have opted into sharing their reviews, they will always show first, then reviews from external sources. Clicking on any review will show you the external review.
![User-Reviews](User-Reviews.PNG "User-Reviews")
![individual-review](individual-review.PNG "individual-review")

### External Recommendations
Kavita+ offers external recommendations on the Series Detail page. The recommendations are aggregated from multiple sources. If the logged in user is an admin with no age restriction, they will be able to see recommendations that are not on the server, otherwise, only series on the server will show (and the usual age restriction or library restriction will apply). 
![recommendations](recommendations.PNG "recommendations")

### External Ratings
Kavita+ offers external ratings. For now, they are just limited to viewing, but may be integrated into activity streams in the future. Here you can see the ratings displayed along side your own review (or lack thereof).
![external-reviews](external-reviews.PNG "external-reviews")


### Scrobbling
Scrobbling is the act of synchronizing certain activities done on a Server, like Kavita, to an upstream provider. As of launch, Kavita+ supports AniList for scrobbling and supports the following events:
- Reading Progress
- Want to Read -> Adds a series to Planning
- Rating a series -> Will map to your rating preferences
- Reviews -> AniList requires reviews be 2200 characters with a tagline of 20-150 characters. If your review doesn't match this, it will not scrobble

To setup Scrobbling, navigate to your User Settings -> Account tab and click Scrobbling. You can add a token for the scrobble provider. You should see a Generate button. This will generate a token for you. Copy and paste this into Kavita and hit save. Once your token is validated, Kavita will show it as set. Tokens are per-user and Kavita will automatically keep them fresh for you. 
![edit-scrobbling](edit-scrobbling.PNG "edit-scrobbling")
![scrobbling-set](scrobbling-set.PNG "scrobbling-set")

---
title: Kavita+
media_order: 'Activate License.PNG,User-Reviews.PNG,individual-review.PNG,recommendations.PNG,external-reviews.PNG,edit-scrobbling.PNG,scrobbling-set.PNG'
visible: true
published: true
---

Kavita+ is an **optional** premium service offered by the main developer of Kavita ([majora2007](https://github.com/majora2007)) which unlocks a set of features for your Kavita application. Kavita+ is a way for me to hopefully go full time on Kavita development—think of it as a way to support the development of Kavita while also getting some sweet features out of it. The goal is to not lock all features behind Kavita+, but add features that otherwise aren't feasible in the base product. The base Kavita application will continue to get frequent updates with new features. 

Kavita+ is a monthly subscription for your individual instance and is node-locked. Once active, all users on your server gain the benefit. You can cancel and resume at any time. 

**Current Features:**
- External Series for Admins
- Remove Donate Link
- Scrobbling Support
  - AniList
- External Reviews
  - AniList
  - MAL
- Recommendations
  - AniList
  - MAL
- External Ratings
  - AniList
  - MAL
  - Google Book (requires Kavita 0.7.6) (In trial to see if valuable for members)

**Planned:**
- Non-manga Book Support
  -  Added: 7/20/23
  - Google Books delivered for v0.7.6. In trial due to poor ratings
  - OpenLibrary to be implemented
- Webhook Support
- Kobo Progress Sync
- Find non-owned series by Person (like Authors)
- Community-Driven Proposed Features (you can submit your ideas on [FeatHub](https://feats.kavitareader.com))

## First time Subscribers
If you are interested, you can use the promo code `FIRSTTIME` for your initial signup for a 50% discount on the first month (2$).

## How to Buy
Navigate to Admin Dashboard -> Kavita+ tab. From there, you can purchase a license via the Buy button. A new tab will open prompting you for your pay information. Kavita+ uses Stripe to handling payments. Kavita team does not have any access to your personal information. Please ensure you use a real email, otherwise you will not be able to receive your product key. Upon finishing subscription, you will receive an email from Kavita with your license key. Move to the Activate step.

## How to Activate
From the Admin Dashboard -> Kavita+ tab, press Activate button. This will prompt you for the email you used with Stripe and the License you received via the email. Enter the details and hit save. This will register your Kavita instance with Kavita+ and should reflect instantly. If you ever need to manage your subscription, like cancel it, you can do so via the Manage button. All management is locked around your email. If for whatever reason your license is showing invalid, use the Check button to re-validate the license.
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

If you do not want scrobbling on a library, as an admin, you can turn it off in Library Settings. If as a user, you want to exclude certain series, you can do that by pressing the scrobbling button on the Series detail page. If you had a series on the scrobble hold list (visible in User Settings -> Scrobbling) and turned it on again, you need to invoke a reading event or rating event, based on whatever you want to scrobble up. You can simply open the reader, go back a page and forward or re-mark an existing item as read.


### How to fix bad Matches
As series can often have many names and users may put their own spin on each one, scrobbling might fail to match. In these cases, there are two options: Correct the Series name or Localized Series name to match AniList or add AniList or MAL weblink to the series. Once done, you can clear scrobble errors and wait. Scrobbling should take after this. You may also want to bust cache in Admin -> Tasks, which will clear bad rating, recommendation, and review data for all your users. 

### FAQ
#### Some reviews look broken
This happens due to a bug in AniList's API. I have created an issue and will monitor. This should be rare and you can use Open Review button to read the review in AniList. MAL reviews do not seem affected.

#### Some series cannot be found
This can happen if AniList doesn't have the series (or you need to rename/add a weblink). If AniList doesn't have a series, you can work with them to add the series. 

### I don't see any ratings, reviews, or recommendations
As of Kavita v0.7.4, only series that exist on AniList will provide external data. I am actively scouting for Comic and Book providers (however it looks unlikely) to provide more information. If you think you have something I can integrate with, please raise it on the feature request site.

#### AniList activity feed isn't showing my progress
AniList currently doesn't show activity if only Volumes were read. You can read more about it [here](https://anilist.co/forum/thread/2586). You can validate that the Volumes do update in the Series on AniList. 

### I have a cool idea
Like all ideas with Kavita, please raise it on feats.kavitareader.com and allow me and the community to expand on it and prioritize it. 

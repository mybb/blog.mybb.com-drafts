# Looking To The Future
As we near the release of MyBB 1.8.27, we’re starting to look towards the future of the Project and where we’re headed. In this post, we’ll lay out our plans going forward.

## 1.8.27 Is a Big Release

The upcoming 1.8 maintenance release is shaping up to be the [second biggest](https://mybb.com/versions/insights/) in the series, with [over a hundred Issues](https://github.com/mybb/mybb/issues?q=is%3Aissue+is%3Aclosed+label%3As%3Aresolved+milestone%3A1.8.27+-label%3Adev-branch) already resolved.

Among others, we have [changes to how the mail queue is processed](https://github.com/mybb/mybb/pull/4210), the [addition of some new PDO based database drivers for MySQL and PostgreSQL](https://github.com/mybb/mybb/pull/4193), [some](https://github.com/mybb/mybb/pull/4326) [additional](https://github.com/mybb/mybb/pull/4257) [plugin](https://github.com/mybb/mybb/pull/4239) [hooks](https://github.com/mybb/mybb/pull/4229), [pagination added to some ACP modules](https://github.com/mybb/mybb/pull/4286), an [alteration to exclude bots and spiders from increasing thread view counts](https://github.com/mybb/mybb/pull/4266), and much more!

We’ve also added some other quality of life enhancements behind the scenes, such as [some automated tools to check PHP syntax for all Pull Requests and Commits](https://github.com/mybb/mybb/pull/4200) to the GitHub repository and some improvements to our support for PHP 8.0.

The release has been a long time coming, but it’s now just around the corner. I’d like to take this opportunity to thank [all of our wonderful contributors](https://github.com/mybb/mybb/graphs/contributors), and to ask a favour: if you can, please test the current code as much as you can! We want to make sure that 1.8.27 is a rock solid release. As usual, once the final Pull Requests are merged, you will find a pre-release thread in the [1.8 Development forum](https://community.mybb.com/forum-165.html).

## The Future of 1.8

With 1.8.27 being such a large release, we’ve been thinking about the future of where MyBB is headed.

As such, we’ve decided that **MyBB 1.8.27 will be the last major release of MyBB 1.8**.

From this point forwards, the 1.8 series shall only receive security fixes and bug fixes for critical bugs that break core functionality.

The reasoning for this change is simple: we need to focus all of our limited resources on one single task - namely, getting MyBB 1.9 released.

## MyBB 1.9

MyBB 1.9 is something we’ve been talking about for a long time (too long, a lot of us would say).

We’ve been working on it side-by-side along with supporting the MyBB 1.8 series, which has unfortunately meant the new release has only had limited attention paid to it.

With 1.8.27 being the last big 1.8 series version, all attention will now be turned to 1.9. There will be a freeze made to the merging of any Pull Requests to the project for a period of roughly two weeks in order to finalise the rebase of MyBB 1.9 to incorporate all of the changes present in 1.8.27.

Once this is complete, attention will turn to the following tasks:

* Scrutinising all new templates to ensure that all changes made to 1.8 in recent releases are reflected in the new templates.
* Tracking down any remaining usages of the old `$templates` based code for templates.
* Writing the ACP management module for the new template system.

Once these tasks are complete, we’ll be at the stage of beginning testing the release in full. At that point, we’ll put a demo install online for everybody to play with, which will reset every day at midnight. This should give everybody a chance to help us debug the release and polish it up.

## An Apology and a Thanks

On a final personal note, I’d like to apologise to the Community for the severe lack of progress with the Project and communication from us.

When I joined, forums were booming and MyBB in particular was abuzz with activity. We had a large bustling Team with members from all over the world contributing many changes and improvements. I’ve watched the Project go from MyBB 1.2 to 1.4; from 1.4 to 1.6 and 1.6 to 1.8. Over that time, things have changed a lot! The rise of social media and smartphones have changed the landscape of internet communities significantly.

Unfortunately, with these changes we’ve seen quite a decline in the progress we’ve made with the Project recently. I wish we had an easy fix to this and we could go back to the activity levels that we’ve seen before, and if anybody has any concrete ideas we’d be very happy to hear them in a constructive manner.

I’d like to take the opportunity to thank everybody who has stuck with us over the years and contributed in any way — be it via financial support on OpenCollective; via bug reports; via Pull Requests; via providing support to other members of the Community; or via any other means. Without you, MyBB simply would not exist.

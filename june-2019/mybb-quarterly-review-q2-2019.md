# MyBB 1.9 Development Update — 2019 Q2

With MyBB 1.8.21 being the [fourth](https://community.mybb.com/forum-165.html) completed release that includes a broader Community effort to improve the stability of the 1.8.x branch, work on MyBB 1.9 continues to move on.

One of the [completed changes](https://github.com/mybb/mybb/milestone/22?closed=1) that will make its way into MyBB 1.9's highlights is the [introduction of modern password hashing](https://github.com/mybb/mybb/issues/3530). The `md5`-based hash function, used in MyBB since its very beginning, will be replaced by `bcrypt`, making it much more difficult to obtain original passwords basing on new hash values in case of a data breach.

The current blocking task for other areas is [rebasing](https://github.com/mybb/mybb/issues/3683) the 1.9 branch on top of the 1.8 branch. Due to the way that Git (the tool we use to manage development) works, 1.9 is worked on in a separate branch whilst 1.8 development carries on in the background. As the 1.8 branch moves forward, the 1.9 branch slowly goes out of sync, missing the recent changes from 1.8.

At the current moment, the 1.9 branch is in line with MyBB 1.8.17, leaving us with 4 versions' worth of changes that we need to merge into 1.9. This, unfortunately, is not an easy process due to the nature of code changes in 1.9 and there are a lot of conflicts which need to be resolved manually. To ease this process we have decided to rebase one version at a time. Some MyBB 1.8 releases contain a smaller amount of changes than others, and these are considerably easier to rebase too.

Once the re-base is complete, there are still a couple of other tasks for 1.9 before we can release our first Alpha and Beta releases. Some of these issues include:

- [Implement a new email system](https://github.com/mybb/mybb/issues/2909). The current MyBB email system causes no end of support threads due to its limited support for slight variations in the way email servers speak the SMTP protocol. We're proposing that we adopt an existing well tested and support email sending library to manage the sending of emails. From a core point of view, this should be relatively simple since almost every email sent uses a single standard function (`my_mail()`).

  We're proposing that we adopt the new [`symfony/mailer`](https://github.com/symfony/mailer) library which provides easy ways to send email via SMTP as well as various email APIs such as Postmark.

- [Review any missed templates from the Twig conversion](https://github.com/mybb/mybb/issues/3684). During the re-base effort, we've noticed some lingering uses of the old template system within the core. These need to be rounded up and eliminated to ensure the template system usage throughout is consistent.

- [Update the ACP to allow editing of Twig template files](https://github.com/mybb/mybb/issues/3686). So far, the Team have all been editing Twig template files directly via the Twig files. While this is a great way to work (who doesn't want to use their own editor of choice?), being able to edit templates easily within the Admin Control Panel is a useful feature that needs updating to work with the new template system. There is some discussion about looking at the JavaScript code editor that we use when editing templates to see if there are any better options on the market. An often requested feature has been the ability to edit multiple templates within tabs at the same time, an enhancement which would be very handy when working with new templates.

  We're also looking at the possibility of leaving certain level of support for the old template format to reduce the number of changes _required_ in MyBB 1.8-based plugins to work with MyBB 1.9.

  Open the [1.9 Theme System Issue](https://github.com/mybb/mybb/issues/3689) issue to see what design problems we'll be aiming to solve and participate in the discussion, whether you're an Extension guru or have previously noticed friction when dealing with themes in MyBB.

  [![View on GitHub](https://blogdotmybbdotcom.files.wordpress.com/2017/10/github.png)](https://github.com/mybb/mybb/issues/3689)

We will also be starting to update and introduce documentation for 1.9. If there are any documentation pages that you would like to see updated or improved, now would be a great time to bring them to our attention!

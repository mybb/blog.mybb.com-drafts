# MyBB Quarterly Review - Q2 2019

Hello, and welcome to the first MyBB Quarterly Review blog post.

You may be wondering what this means? We realise that we've been pretty poor at keeping the community abreast of what's going on in the project recently, which is something we want to rectify. Our plan from here on out is a continuous series of blog posts — one every quarter — that cover the goings on within an around MyBB. These posts won't only be focused upon the MyBB core, but will also highlight notable plugins, themes and user contributions.

As this is new to all of us, I'm sure it'll take some time to get used to and to settle into a consistent format. We'd welcome any feedback on the kind of content you'd like to see in these posts and ways we can improve the way we present the project and what's going on!

## 1.8 Development Update

MyBB 1.8 continues to tick along. As of the time of writing, we're putting the finishing touches on MyBB 1.8.21. We have only one issue currently open on [the associated milestone](https://github.com/mybb/mybb/milestone/28) which we plan to have resolved shortly.

1.8.21 is quite a big release, with a total of 37 closed issues — not all of which are simple bug fixes. For example, **@effone** [has added support](https://github.com/mybb/mybb/issues/3681) for the [JSON Feed](https://jsonfeed.org) format for syndication along with fixing some syndication related issues. We also have [the latest version of SCEditor](https://github.com/mybb/mybb/issues/2542) integrated in the core, along with an [update to the current version of jQuery](https://github.com/mybb/mybb/issues/3640) — again thanks to **@effone**!

We're also re-thinking our approach to releases. We currently release new versions when we reach a decent number of closed issues. This can sometimes mean there is a long wait between releases. For example, there were 5 months between releasing MyBB 1.8.19 and 1.8.20.

We're proposing that we move to a more strict release schedule, with a new release being made available every 2 months regardless of the number of closed issues. Milestones on GitHub would be assigned due dates, and if we neared the end of a due date with issues left open, these would be moved to the next milestone instead of blocking a release (except in the case of serious bugs). We would continue with our recent trend of releasing pre-release packages to the community via the forums. We hope that having a regular release schedule may help keep team activity trickling along rather than coming and going in waves as it currently does.

## 1.9 Development Update

Work on MyBB 1.9 continues to move slowly. The current blocking task is rebasing the 1.9 branch on top of the 1.8 branch. Due to the way that Git (the tool we use to manage development) works, 1.9 is worked on in a separate branch whilst 1.8 development carries on in the background. As the 1.8 branch moves forward, the 1.9 branch slowly goes out of sync, missing the recent changes from 1.8.

At the current moment, the 1.9 branch is in line with MyBB 1.8.16. As we mentioned in the previous section, we're currently preparing to release 1.8.21. This leaves us with 5 1.8 versions' worth of changes that we need to merge into 1.9. Unfortunately, this is not an easy process due to the nature of the changes in 1.9. There are a lot of conflicts which need to be resolved manually. To ease this process we have decided to rebase one version at a time. We've already jumped from 1.8.15 to 1.8.16 and plan to [jump to 1.8.17](https://github.com/mybb/mybb/issues/3683) then 1.8.18 within the next week. Some MyBB 1.8 releases contain a smaller amount of changes than others, and these are considerably easier to rebase too.

Once the re-base is complete, there are still a couple of other tasks for 1.9 before we can release our first Alpha and Beta releases. Some of these issues include:

- [Implement a new email system](https://github.com/mybb/mybb/issues/2909). The current MyBB email system causes no end of support threads due to its limited support for slight variations in the way email servers speak to the SMTP protocol. We're proposing that we adopt an existing well-tested and supported email sending library to manage the sending of emails. From a core point of view, this should be relatively simple since almost every email sent uses a single standard function (`my_mail()`).


	We're proposing that we adopt the new [`symfony/mailer`](https://github.com/symfony/mailer) library which provides easy ways to send email via SMTP as well as various email APIs such as Postmark.
- [Review any missed templates fro the Twig conversion](https://github.com/mybb/mybb/issues/3684). During the re-base effort, we've noticed some lingering uses of the old template system within the core. These need to be rounded up and eliminated to ensure the template system usage throughout is consistent.
- [Update the ACP to allow editing of Twig template files](https://github.com/mybb/mybb/issues/3686). So far, the team have all been editing Twig template files directly via the Twig files. While this is a great way to work (who doesn't want to use their own editor of choice?), being able to edit templates easily within the ACP is a useful feature that needs updating to work with the new template system. There is some discussion about looking at the JavaScript code editor that we use when editing templates to see if there are any better options on the market. An often requested feature has been the ability to edit multiple templates within tabs at the same time, an enhancement which would be very handy when working with new templates.

We will also be starting to update and introduce documentation for 1.9. If there are any documentation pages that you would like to see updated or improved, now would be a great time to bring them to our attention!

## Community Update

*... TODO ...*

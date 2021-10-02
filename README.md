[![MyBB](https://raw.github.com/mybb/mybb/feature/images/logo.png "MyBB")](https://mybb.com "MyBB")

# MyBB Development Blog Drafts

This repository is used to manage and prepare blog posts for the [MyBB Development Blog](https://blog.mybb.com).

## Drafting a post

A member of the team will create a new branch from `master` in this repository (not a fork), named with a *short* title for the post using [kebab-case](https://en.wikipedia.org/wiki/Letter_case#Special_case_styles).

The initial draft will be made by creating a new file using the same short title with a `.md` extension in the appropriate `YYYY-MM` directory.

The intended long title will be used as a main heading in the markdown file, allowing suggestions to be made, followed by the main body of the post.

```markdown
# Long title

...body
```

Note that the post should not be signed off at the end of the body.

After committing the intial draft and pushing the branch a Pull Request will be made to `master` where discussion and suggestions can take place. Large suggested changes can be made by the community by creating Pull Requests to the draft branch.

## Merging a draft into master

When a draft is merged into `master` it simply means that it is in an acceptable form to be published. This does not mean that the post will be published on the blog immediately and other changes can still be suggested.
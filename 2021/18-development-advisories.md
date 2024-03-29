# 1.8's CAPTCHA Bug, Parser Validation, and PHP Compatibility

As we stabilize the 1.8 branch for future support with development eventually [switching focus](https://blog.mybb.com/2021/05/17/looking-to-the-future/) to 1.9, we'd like to draw your attention to the following advisories.

## CAPTCHA Bug

MyBB 1.8.27 has introduced a [bug](https://github.com/mybb/mybb/issues/4458) affecting two of MyBB's supported CAPTCHA mechanisms: ***reCAPTCHA v3*** and ***hCaptcha invisible***. For those, the CAPTCHA may appear broken, and the verification can reject or accept attempts incorrectly.

If your forum uses those systems, we advise to either:

- temporarily switch to another mechanism using the **CAPTCHA Images for Registration & Posting** setting (ACP: _Configuration → Settings → General Configuration_), or
- applying the [upcoming changes](https://github.com/mybb/mybb/pull/4456/files) to source code files manually.

This problem will be resolved in the next maintenance release.

## Parser Output Validation

The upcoming maintenance release enforces validation of XHTML code generated by the MyCode parser in order to improve security.

MyBB 1.8.27 [included](https://github.com/mybb/mybb/issues/4305) this feature in report-only mode, meaning that any problems are already being saved to the [configured error log](https://docs.mybb.com/1.8/faq/errors/#enabling-error-logs). After upgrading, validation errors will continue to be logged, but messages with problematic MyCode will not be displayed to prevent potential XSS attacks against your forums.

Forum administrators should verify that their error logging is configured properly, and monitor the log for errors that may indicate necessary changes to their customizations like custom MyCodes, theme templates, username styles, and plugins. These errors can be triggered when forum content that uses MyCode is viewed.

We created a [relevant Docs section](https://docs.mybb.com/1.8/faq/errors/#parser-output-validation-failed) that details pinpointing the origin, debugging using a dedicated tool, and disabling the validation requirement for boards that are not yet ready for this change.

### Fixing Validation Errors

To help demonstrate what actions may need to be taken, let's take a look at some cases that turned up so far:

- #### Case 1: Attributes Without Value in Default Templates
  MyBB's default theme included HTML attributes without values. These caused validation errors such as:

  - `Specification mandates value for attribute`
  - `attributes construct error`

  To fix this, we simply added `="true"` fragments [in this commit](https://github.com/mybb/mybb/pull/4337/commits/432ecc2c1213120b3759cfa7c99db898b0da2752).

- #### Case 2: Redundant Tags in *Username Style*

  In a [support thread](https://community.mybb.com/thread-232787.html), unnecessary HTML in a customized username style, present in a forum post, resulted in a logged failure that mentioned:

  - `Opening and ending tag mismatch`
  
  - `Extra content at the end of the document`
  
  This could be resolved by cleaning up the HTML code in the *Username Style* field for the problematic user group.
  
- #### Case 3: Self-Closing Tags in Custom MyCode

  In another [support thread](https://community.mybb.com/thread-232812.html), a custom MyCode included an unclosed `<hr>` HTML tag, which resulted in a validation failure that mentioned:

  - `Opening and ending tag mismatch`

  - `EndTag: '</' not found`

  For correct XHTML validation, tags that don't have an equivalent closing tag should include a forward slash: `<hr />`.

- #### Case 4: Invalid Placeholder Format

  A plugin that inserted invisible markers in the `<example#0>` format resulted in errors referring to attribute parsing and missing end tags. This format was [changed](https://github.com/dvz/mybb-dvzMentions/commit/ffa4f15f885eb604f014001b7cdc6ea47d5b0fc3) to `<example id="0" />` to pass the validation.

## PHP Compatibility

MyBB aims to support most recent versions of web browsers, servers, database systems, and PHP interpreters. Due to [significant changes](https://www.php.net/manual/en/migration80.incompatible.php) in PHP 8.0, however, we [recommended](https://docs.mybb.com/1.8/install/requirements/) using PHP up to 7.4 while the code was being adjusted.

The upcoming MyBB release includes another batch of such adjustments, and removes some unnecessary [side-effects](https://github.com/mybb/mybb/issues/4428) of version-related PHP *Warnings*. We also pay attention to [PHP 8.1](https://wiki.php.net/todo/php81), which is not expected to cause major problems.

Even though more issues may still be discovered when running MyBB on latest versions of PHP, we encourage administrators and extension developers to verify the stability of their forums and extensions on PHP 8, and to watch out for any errors that may appear in the [error log](https://docs.mybb.com/1.8/faq/errors/#enabling-error-logs), starting with the next maintenance release. Numerous web hosts already support switching to PHP 8.0, and MyBB can easily be tested [locally using Docker](https://github.com/mybb/deploy/tree/dev).

Any suspected issues related to compatibility, as usual, can be reported on our [support platforms](https://mybb.com/support/).

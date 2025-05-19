**1)** Where would you fit your automated tests in your Recipe project development pipeline? Select one of the following and explain why.
  1. Within a Github action that runs whenever code is pushed 
  2. Manually run them locally before pushing code
  3. Run them all after all development is completed

*Response.* I would choose **option 1**, running GitHub actions on push. More specifically, there will be `dev` and `main` branches—only on those branches would pushes trigger the action. 

In this way, I make sure:
- The actions aren't triggered too often: not every change demands a whole UI check, only important, larger changes that get merged into `dev` require checks.
- The process is automated: where the code's correctness matters (by merging into more critical branches), this can be automated as a "check" that prevents any further changes if anything goes wrong.

**2)** Would you use an end to end test to check if a function is returning the correct output? (yes/no)

*Response.* **No,** I would not use end-to-end tests to check if a function returns the correct output. Especially for smaller functions with clear expectations for its output that run independent of rendering, networking, state managemenent, etc., **unit tests** would best suit the scenario.

**3)** What is the difference between navigation and snapshot mode?

*Response.* The (default) navigation mode loads a page from scratch completely, with page navigations. In contrast, the snapshot mode simply "snapshots" the current page at the current state and, as such, excludes performance metrics.

**4)** Name three things we could do to improve the CSE 110 shop site based on the Lighthouse results.

*Response.*
- Optimize static image assets: prepare various image sizes for mobile and desktop and fetch and render accordingly to minimize unnecessary large assets.
- Add `<meta name="viewport">`: Adding this tag can help mobile users' experiences, by optimizing everything from fonts to "prevent[ing] [a 300 millisecond delay to user input](https://developer.chrome.com/blog/300ms-tap-delay-gone-away/?utm_source=lighthouse&utm_medium=devtools)."
- Add the `lang` attribute to the `<html>` tag: Adding the `lang` attribute helps accessibility by allowing screen readers to interpret the correct language of the site, which is English (`en`) in this case.

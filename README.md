# SC (Web)App Guidelines

## ✨ SWAG ✨

**S**C (**W**eb)**A**pp **G**uidelines (🗿 SWAG) are here to help you give your next project some coolness and #swag in the real world.

As frontend developers, we often deal with all sorts of the designs. Some designs cover different states, mouse/touch actions, errors and error messages, empty states, filter values, etc. But, more often than not, designs show only the best case scenarios. If the design doesn't show _at least_ most common possible states of the app, **it should be your job** to provide a decent UX for the end user.

> In a blue-themed app, it's better to have a yellow disabled button, than no disabled state at all!

Yes, it's better to make an "ugly" version of some not-defined-in-design state than to completely omit it. You probably stumbled upon a website or an app that had a button that looked like it doesn't do anything, even though it did some actions in the background. You also probably didn't like that experience. Don't. Be. That. Guy.

Should have the designer design that missing piece of the puzzle? Probably. But it's not entirely their fault. Everyone makes mistakes. Normal users have been in touch with _a lot_ of apps. We as developers probably even much more. We should use our skills to make the experience for non-dev folk as pleasent as possible and as intuitive as possible. Users love when the app interacts with them and they know what's happening in the moment. Or what will happen. Or what did happen. Probably you love it too.

## Forms

Forms are probably one of the most underdesigned parts of any app. Probably because there is so much to it. So let's go through the anatomy of a typical form.

### Validation

Every form has at least one input field. Imagine the simplest variation of a form - newsletter subscription. It has one (email) input field and a (submit) button "Subscribe". Newsletter subscription comes to your email, so you need to provide a valid email. That means that nothing that doesn't qualify as an email should be submitted through the form.

- [ ] Validate the input field so it falls under the restrictions set for the value from that field (e.g. valid email, strong enough password, special characters in names, etc.).

Whenever possible, try to use real-time validation i.e. while user is typing or the current modified field loses focus. If the field is invalid, user should be notified.

- [ ] If the input field is invalid, denote it in a common way (e.g. red outline, red exclamation point icon, etc.).
- [ ] Whenever possible, show, for each field, what exactly is wrong with that field (e.g. a small error message below a field).

> Even if the design doesn't have the necessary colors, use those that somewhat fit with the design that you have.

That way, user will be aware that something went wrong.

- [ ] If the form is invalid, make sure to disable the submission of the form.
- [ ] Style the button in a way that user would know that the submission is disabled (e.g. grayed out, reduced opacity, not-allowed cursor, etc.).
- [ ] If possible, when user tries to click the submit button, try to bring into field of view the first input field that is red, i.e. that is invalid, so that user has a better sense of what needs to be updated.

### Actions

Forms are to be interacted with. Interactions should be presented to a user in a noticeable way.

- [ ] Whenever something is happening with the form (e.g. submission is in progress, data is being fetched, etc.), denote it in some way (e.g. loading spinner in a button, loading spinner over the form, change text in a button to denote what's happening, etc.).
- [ ] If an action succeeded or failed, user should be aware of it (e.g. toast message, page redirect, etc.).

### Field information

Forms usually have a lot of fields. It's common sense that users should now what each field is for. It would be even better if user knew what kind of data format is expected.

- [ ] Use labels above the fields to denote what's the field for (e.g. email, password, URL, etc.).
- [ ] Use placeholders to show to the user what kind of data is expected (e.g. "name@example.com" for email, "https://example.com" for URL, etc.).
- [ ] Show any field requirements with additional descriptions/icons (e.g. password strength requirements, toggle password visibility, etc.).

## Responsivness

One of the worst things that can happen is that client or a user opens an app, looks at the screen and says: "This is sh*t!" (this actually happened to us, true story). Each component should fit almost every resolution. We say "almost" because some components are either obsolete on a certain resolution or they change their structure completely. The following rules apply to even the smallest, atomic, dumb components.

- [ ] Fairly obvious, but components need to be _pixel perfect_, meaning they should be as close to the design as possible.
- [ ] When working on a component, test it thoroughly through a range of different viewport sizes (every browser has a support for that; even if it doesn't, shrink/enlarge the entire window). It needs to look _good_ and **not broken**.
- [ ] If the design doesn't provide the look and feel for a component on a certain resolution - use your common sense and make it usable.
- [ ] If you're not making a horizontal slider or something similar, **`overflow-x`** is your enemy! User should scroll only Y axis i.e. up and down.

We didn't talk about breakpoints. And we probably shouldn't. Breakpoints are just numbers, screen size values which help determine where should the component change it's look and feel.

- [ ] If the component really "sticks out" on a certain resolution, introduce a new breakpoint, even if the design doesn't cover it. **But don't overdo breakpoints!** If you find yourself needing to do this constantly, it's probably due to the bad design (#nohate).

## Error handling

Erros happen... a lot. A lot more than us developers anticipate. That's why you should _always_ handle errors, in any way possible.

- [ ] Always account for errors, in even the smallest sections of the app.
- [ ] If the error is unexpected i.e. neither frontend nor backend account for it, show a generic message that something went wrong (e.g. when 500 happens).
- [ ] Whenever possible, account for different errors from both frontend and backend. Catch them! Identify them by using anything even remotely unique (e.g. status code, error ID, etc.).
- [ ] When an error happens, users usually freak out. Provide them alternatives (e.g. reload the page, try again, etc.).
- [ ] Simply put, don't let errors completely kill your app.

## Empty states

Tables, charts, grids... all of it looks awesome when there is enough data to display inside. But what if the cart is empty? Or there are no blog posts? Or you cleared your last financial report?

- [ ] When something is empty, we don't want it to be literally empty i.e. don't show a blank page to a user. Show a nice message, maybe a picture or an icon.
- [ ] When applicable, show an action that would encourage user to create/update the list/state that is empty.

## Visual states

Hover, active, focus,... states should be part of the every app. It's the main visual tool for the user when they interact with the app.

- [ ] Implement different button/inpuyt/component states. Even if the design doesn't provide it, use something intuitive (e.g. lighter color for hover and darker for focus, outlines, shadows, etc.)
- [ ] Whenever possible, "ease" something into user's field of view (don't just pop it in). Animations and transitions come in handy there.

## Performance

When writing components, always make sure to write it as good as possible, performance wise. Give yourself some time to think and come up with a better, optimized solution. Every little thing counts and usually adds to the complexity of the app.

- [ ] Beware of the loops! Whenever possible, use as much caching as possible and as few loops as possible.
- [ ] Use guard clauses, to escape from the code block as soon as possible. Why would you go and check something if it's unnecessary?
- [ ] Often check for memory leaks (e.g. infinite loops, unused subscriptions, etc.).
- [ ] Watch out for the async code! Make sure that it actually runs async, so it doesn't block the main thread, i.e. hang your app.

> Loops are generally the biggest killer. For example, if you have a loop that needs to iterate over a 1000 items, and for each items needs to iterate over 50 items, the code will be executed 50 * 1000 = 50000 times! Sometimes, this is unavoidable, but more often than not, an algorithm can be rewritten to save up on some resources.

## "What if..."

As a developer, you should always ask yourself "what if" and think ahead. You are the developer, yes, but you're also a user. And when developing/testing applications, you should often put yourself in the shoes of an unexperienced user. You can not expect from the user to completely understand your ideas in the app if they're seeing the app for the first time. Here's a list of some common questions you might ask yourself. Please come up with some of your own as well.

**What if...**
- ...user doesn't provide all the necessary data?
- ...user doesn't see a response for while because of their slow connection?
- ...user cancels the operation before it's done?
- ...user loses network connection while the operation is in progress?
- ...user has a really small phone or a really large monitor?
- ...user tries to open the app in an old browser?
- ...

## Definition of Done (a.k.a. DoD)

Component is done when it's done. But _when exactly_ is the component done? There are a few _trivial_ keypoints:

- [ ] Component looks pleasing, easy on the eyes, and fits with the rest of the design/page(s).
- [ ] Component makes sense, i.e. it's logical and functional.
- [ ] Component is performant.
- [ ] Component is fully usable, regardless of the browser, platform or the device.
- [ ] Component is stress-proof, meaning it's not easily breakable by a trivial/common user mistake.
- [ ] Component was tested by a developer multiple times over the course of the development.
- [ ] Component passes _all_ the acceptance criteria.
- [ ] Component edge cases are covered (at least most of them).
- [ ] Component _feels_ done and production ready.

Then, and only then, the component is ready for the QA.

## Commnuication

Last but not least - communicate! Talk to the designer, other developers, your lead, project manager, etc. Discuss about the problems you encountered and dilemmas that you have. More heads are always smarter than one. It's better for you and your team to say "This is sh*t!" for something than for the client to do the same.
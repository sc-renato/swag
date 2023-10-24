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

> Even if the design doesn't have the necessary colors, use some that somewhat fit with the design that you have.

That way, user will be aware that something went wrong.

- [ ] If the form is invalid, make sure to disable the submission of the form.
- [ ] Style the button in a way that user would know that the submission is disabled (e.g. grayed out, reduced opacity, not-allowed cursor, etc.).
- [ ] If possible, when user tries to click the submit button, try to bring into field of view the first input field that is red, i.e. that is invalid, so that user has a better sense of what needs to be updated.
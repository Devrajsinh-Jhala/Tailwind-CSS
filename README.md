This Repo is made to ink my learnings and Projects while following Tailwind CSS course by CodeWithHarry.

👉 Important Points:
Use Tailwind Intellisense Extension and to use that first install Extension and then run following commands:

✔ npm install -D tailwindcss postcss autoprefixer
✔ npx tailwindcss init
👉 This will create tailwind.config.js where do this in content: ["*"]

✔ These utilities are really just a shortcut for adding margin to all-but-the-first-item in a group, and aren’t designed to handle complex cases like grids, layouts that wrap, or situations where the children are rendered in a complex custom order rather than their natural DOM order.

This means that if you use ul mx-3 -> li li li then this mx-3 will not apply to 1st li so instead leave 1st li blank or give classes to each children

✔ Always go for mobile first approach while using Tailwind

✔ Square Bracket Notation:
👉 If you want to insert custom CSS attributes like m-162px etc. use mx-[162px]. Dont forget to specify units like px,rem,em.

✔ In tailwind first make for small devices then move to larger ones.
👉 Don't use 'sm:' to target mobile devices
👉 Use unprefixed utilities to target mobile, and override
them at larger breakpoints

✔ If in button there are too many classes then you can replace them with single class btn(any name) then in .css write:
.btn{
@apply all classes as it is
@apply font-bold py-2 px-4 rounded #{!important}; (example)
}

✔ Tailwind will automatically move any CSS within a "@layer" directive to the same place as the corresponding @tailwind rule, so you don’t have to worry about authoring your CSS in a specific order to avoid specificity issues.
👉 This means if you write:
@layer utilities{
.btn{
@apply all classes as it is
@apply font-bold py-2 px-4 rounded #{!important}; (example)
}
}
This will push the code at the end of utilities layer if you write components it will push at components layer.

❌ Dont Overuse these as it costs your maintaibility of code

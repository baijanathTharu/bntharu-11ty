---
title: Must prefer union of interfaces to interface of unions
date: 2022-06-27
image: /assets/images/2021/code.jpg
---

Let us see a example:

```ts
interface Gender {
    title: "male" | "female";
    clothing: MaleClothing | FemaleClothing;
}

interface MaleClothing {
    // some properties...
}
interface FemaleClothing {
    // some properties...
}
```

Here `Gender` interface is a interface of unions and it has few problems such as title can be `male` with clothing `FemaleClothing` and title can be `female` with clothing `MaleClothing`. So it is error prone. In such cases, we can prefer union of interfaces as below:

```ts
interface Male {
    title: "male";
    clothing: MaleClothing;
}
interface Female {
    title: "female";
    clothing: FemaleClothing;
}

type Gender = Male | Female;
```

By using `union of interfaces`, we have eradicated the error that we had peviously.

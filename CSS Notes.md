1. What is CSS Selector?
   
-> A CSS selector is a pattern used to select and style HTML elements. Selectors tell the browser which elements the CSS rules apply to.
    Here's a quick overview of common types of CSS selectors:
   ![image](https://github.com/user-attachments/assets/c6e36ac3-bf01-4add-997b-4c59905f099e)
   ![image](https://github.com/user-attachments/assets/7527af3d-26e1-4480-b680-62fe845fa2c0)
   ![image](https://github.com/user-attachments/assets/987ef599-9651-420c-be6d-b1843507b3c8)
   ![image](https://github.com/user-attachments/assets/07f023e0-fe68-409b-ae26-f0f14eb1fa68)
   ![image](https://github.com/user-attachments/assets/5ab0a6cd-fcc4-4a51-9d6a-1b6f68074d02)
   
   There are 5 selector type, these are few example to understand them, there are more of such type.

2. What is the difference between relative, absolute, fixed, and sticky positioning in CSS?
   ->
   ![image](https://github.com/user-attachments/assets/f787ee61-187b-4bc7-9343-bfe5b8019121)
   ![image](https://github.com/user-attachments/assets/b31471fa-a1ed-4cf7-8bae-8fd90c4c7cbf)
   ![image](https://github.com/user-attachments/assets/da925a26-c335-4032-ab5d-049272e645b8)

3. What is specificity in CSS and how is it calculated?
   -> ![image](https://github.com/user-attachments/assets/4b44727c-8242-4595-85cc-62d0c509ac3c)
      ![image](https://github.com/user-attachments/assets/34a6300d-3913-4afc-9ab4-76e88080e23f)

4. How do media queries work in responsive design?
   -> Media queries are a feature in CSS that let you apply styles only when certain conditions are true — such as screen width, device          type, orientation, or resolution. They are the core of responsive design, allowing websites to adapt their layout and appearance           across different devices.
      Eg:-
            @media (condition) {
              /* CSS rules go here */
            }
   ![image](https://github.com/user-attachments/assets/1846a607-0836-4889-85a6-cb46ce257f5f)
   ![image](https://github.com/user-attachments/assets/64b629e3-2222-4f9a-a940-c71b0d6c4e52)

   🌍 Why Use Media Queries?
   
       -  Ensure content is legible and usable across devices.
       -  Avoid horizontal scrolling on mobile.
       -  Adapt layouts, font sizes, image scaling, and navigation design.
       -  Improve user experience and SEO (Google prioritizes mobile-friendly design).

      ![image](https://github.com/user-attachments/assets/4ef3bb0e-1eff-49c1-9b93-4473efadbe60)

5. How to center a div?
   
   --> Using Flex-box:-
   ![image](https://github.com/user-attachments/assets/bb597010-1259-445c-8e89-5485885aab36)
   ![image](https://github.com/user-attachments/assets/84a1c8c0-5e77-487a-8f9a-b322b1cc431e)

   Here, justify-content to center for horizontal centering (on the inline axis).
   Set align-items to center for vertical centering.
   
   ** Using Grid:-
   
      ![image](https://github.com/user-attachments/assets/0804063d-c2c0-417d-bff1-29cb81f3a7ba)
      ![image](https://github.com/user-attachments/assets/a2cd5a12-a8bf-41e7-85ba-0ce530541eb0)


   For more reference:0 https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_cookbook/Center_an_element

   Using POsition:-
   
      ![image](https://github.com/user-attachments/assets/4ea21acc-1343-4c65-986d-fd01baeebdc5)

   Tested code on live Html:-
      <div class="outside">
           <div class="inside">inside</div>
      </div>

      css:-
   .outside {
     display: flex;
     justify-content: center;
     align-items: center;
     height: 100vh
   }

   Using Position:-
   .outside {
     position: absolute;
     top: 50%;
     left: 50%;
     transform: translate(-50%, -50%);
   }
      



   


5.  How does the z-index property work?
   
      --> The z-index property specifies the stack order of an element.
    z-index controls the stacking order of positioned elements on the z-axis (front to back).

Higher z-index = Closer to the viewer = Appears on top of elements with a lower z-index.
An element with greater stack order is always in front of an element with a lower stack order.

Note: z-index only works on positioned elements (position: absolute, position: relative, position: fixed, or position: sticky) and flex items (elements that are direct children of display:flex elements). Does not work on position: static. z-index Default value:	auto.
Inherited:	no

Note: If two positioned elements overlap without a z-index specified, the element positioned last in the HTML code will be shown on top. 

6.Explain stacking context, positioning, and nesting.

->> https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_positioned_layout/Stacking_context
A stacking context is a three-dimensional conceptual layer in which HTML elements are stacked on top of one another along the z-axis (the axis perpendicular to the screen).

Think of it like a stack of cards — each stacking context is a separate deck, and elements inside it are arranged relative to each other, but they can’t overlap elements outside their deck unless the parent stack is higher.

A stacking context is a self-contained environment where the z-index of elements is only compared within that context.

![image](https://github.com/user-attachments/assets/4f1ee76a-30e5-4d2b-9770-ad180dc1effe)
![image](https://github.com/user-attachments/assets/1c8bf54d-4a50-4e7b-9b43-38c631614c99)
![image](https://github.com/user-attachments/assets/a7351996-021a-4c15-af1a-50508a3dcdde)




7. What is a reflow (layout thrash), and how can you minimize it in CSS?
   --> Nesting refers to placing one HTML element inside another — for example, a child <div> inside a parent <div>. Each nested element        inherits or creates its own stacking behavior, depending on how the parent behaves.
      When you nest elements inside a parent that creates a stacking context, those elements:
      Are confined to that stacking context

Cannot be visually stacked above elements outside that context — no matter how high their z-index is
9. What are CSS custom properties (variables), and why use them?
10. What is the difference between em, rem, %, vh, and vw units?
11. Explain how these units relate to font size, parent size, and viewport.












    
    

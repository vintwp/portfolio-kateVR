1. ### KateVR Project ### - [LINK](https://vintwp.github.io/portfolio-katevr/)
2. Uses Swiper for swipers (hero section, about section);
3. Uses Custom made slider (tabs) for purchase block;
4. Uses 16-column for XL devices, 12-column for desktop, 6-column for tablets and 2-column for mobile design
5. Accordion, dropdown, form validation, modals are independent (you can add new components in layout. But you should anounce new constants and functions)

  For example:

  ```javascript
    // Forms validation
    const form = document.querySelector('.form');

    contactForm.addEventListener('submit', e => {
      e.preventDefault();

      if (validateWholeForm(contactForm)) {
        contactForm.reset();
      }
    });
  ```

  ```javascript
  // Dropdown

    initializationDropDownIcons();
    initializationDropDownOptions();
    initialValuesInDropdowns();
  ```

  ```javascript
  // Accordion

    const accordion = document.querySelector('.accordion');
    const accordionItem = document.querySelectorAll('.accordion__item');
    let accordionItemOpened = false;

    accordionItem.forEach(accordItem => {
      accordItem.addEventListener('click', (e) => {
        const currentItem = e.target.closest('.accordion__item');
        let activeItem = accordion.querySelector('.accordion__item.opened');

        if (activeItem !== currentItem && accordionItemOpened) {
          closeAccordion(activeItem);
          openAccordion(currentItem);
        }

        if (activeItem === currentItem) {
          closeAccordion(accordItem);
          activeItem = currentItem;
          accordionItemOpened = false;
        }

        if (!activeItem && !accordionItemOpened) {
          openAccordion(accordItem);
          accordionItemOpened = true;
        }
      });
    });
  ```
  ```javascript
  // Modal

  // No need to create consts and launch functions. Your should keep structure in html
  ```

  6. List of countries and cities are received from json file.
  7. Swiper for hero section *are disabled in mobile*
  8. SVG icons inserted with SVGInjector and you could use fill method
  9. Uses scss extends and mixins

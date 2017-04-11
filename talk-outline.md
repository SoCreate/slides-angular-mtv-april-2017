### Introduction

I'm Justin Schwartzenberger. Lead Engineer at a company called SoCreate, where we are building a 
screenwriting platform for motion picture, tv, webisodes, etc.

I am also the host and maintainer of AngularAir, a weekly live videocast that explores approaches, 
patterns and tech through discussion and demos.

I am also also a trainer and author and have courses on Pluralsight and Lynda.com for Angular training.

And, I just got back from ngconf where I was a speaker for the second year in a row. This year 
I spoke about embracing component tranquility. Understanding the price we pay to componentize and 
finding ways to become component architects.

I Will be speaking at ng-cruise about template and reactive forms.

### Components

Let's talk about some of the cool things about components.
- encapsulation
  - logic
  - styling
- reusability
  - inputs and outputs

Let's talk about some of the challenges about components.
- component tree
- coupling

Challenges building with components.
- need to spin up whole app
- need to nav to screen that has component
- need to know if it can be reused

How can we solve this workflow
- identify what it is
- provide a way to work in isolation

### Playground for Angular

Playground for Angular
- how it came to be
- what it is
- where to find it

### Demos
- create a sandbox and inline component (`WelcomeComponent`)
  - add a scenario ("first scenario")
  - directive (`HighlightDirective` with `@HostBinding('style.background-color')`)
  - pipe too (`NgifyPipe` with `return 'ng-${value}';`)
- create sandbox by a component (`ng g c shared/address -it -is --no-spec --flat=true` and add `@Input() address` and `<address>`)
  - add scenarios
    - "no address" (show error in browser then add `ngIf` on `<address>`)
  - show **context**
    - add scenario "basic address" and add `context: address: {attentionTo, street, city, state, postal}`
    - add scenario "with attention to" and copy context address
    - add scenario "on click" and add `(click)="log(address)"` and `context: log(i) {console.log(i);}`
  - mention "host" component concept
    - update component to have `styles: [`:host(.awesome) {color:green;}`]`
    - add scenario "is awesome" and add `<ex-address class="awesome">`
- show scenario settings (create `.add()` scenarios for each)
    - **styles** (`styles: ['ex-address {color:red;}']`)  
        (these are for the host "parent")
    - **providers**  
        (create service `ng g s shared/address-lookup --no-spec --flat=true -m shared/shared.module` and inject service in `AddressComponent`)  
        (show without using `providers` yet...get error in browser)  
        (add `providers: [AddressLookupService]`)
        (create a `MockAddressLookupService`)
- show sandbox settings
    - create `SelectAddressComponent` (`ng g c shared/select-address -it -is --no-spec --flat=true` and form html)
    - **imports** (`imports: [FormsModule]`)
    - add `<ex-address>` to template
    - **declarations** (show in browser to show provider dependency error)
    - **providers** (add `providers: [AddressLookupService]`)
    - **prependText** (add "featureA")
- quick recap of use case (to help explain lack of discovery)
- deep linking (explain url for selected scenario)
- embed mode (`&embed=1`)
- show example discovery app

### Where to from here with the Playground project?
- some clean up of the source code
- spruce up the example apps
- add some more to the docs site

### Wrap up

Thank you!

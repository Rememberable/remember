# Frontend

## Architecture's types

### Classic architecture

* pages
* api
* helpers
* store
* hooks
* assets

Use when:

1) Small team
2) One time project
3) Simple project

### Module simple architecture

Pages

Modules:

1. ArticleComments - consist of api, components, helpers, store
2. RegistrationForm - consist of api, components, helpers, store
3. etc.

Components:

1. UserCard
2. ProductItem
3. Comment
4. etc.

UI:

1. Button
2. Input
3. Select
4. etc.

### Atomic design

The overlying layers strictly use the underlying ones!!!

* pages
* templates
* organisms
* molecules
* atoms

### Feature Sliced Design

The overlying layers strictly use the underlying ones!!!

app - Initializing application logic.

pages - Application Pages.

processes - (Optional) Application processes running on pages.

widgets - Independent and full-fledged blocks for pages:

1. SideBar
2. Header
3. Footer
4. PostCard

features - (Optional) Custom scripts to process:

1. AuthByPhone
2. ArticleFeedback
3. ChangePhoneForm

entites - (Optional) Business entities operated by the subject area:

1. User - consist of api, components, helpers, store
2. Article - consist of api, components, helpers, store
3. Product - consist of api, components, helpers, store
4. Order - consist of api, components, helpers, store

shared - Reusable modules without reference to business logic

- Example:

features/widgets - ProductComment

entites - ProductList + ProductForm

shared - Input + Button
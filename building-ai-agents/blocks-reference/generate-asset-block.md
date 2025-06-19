---
description: Generate HTML assets.
---

# Generate Asset Block

The Generate Asset block allows users to generate designs and PDFs from a source HTML document.&#x20;

## Configuration&#x20;

### Source Document&#x20;

Provide the source document that will generate your design. Types of allowed source documents include:

1. HTML Document
2. Markdown
3. Single Page Application (SPA) Bundle&#x20;

Variables can be included in the source document.

#### The HTML Developer Environment&#x20;

By selecting the expand icon within the source document area, you can open a full screen development environment to easily edit the HTML.&#x20;

<figure><img src="../../.gitbook/assets/expand code.png" alt="" width="375"><figcaption></figcaption></figure>

The developer environment provides you with additional capabilities:

**Generate HTML:** Generate HTML code based on a text prompt. You can specify any variables that you'd like to be used in the asset.

**Modify HTML:** Edit and update your HTML code with a text a prompt.&#x20;

**Test Data**: Pass test data through the block and see the output results.

### Output

Configure the output settings for the Generate Asset block.

#### Output Variable&#x20;

Provide an output variable name for the generated result. Example: `Asset_1`

#### Format

Select the output format for the generated asset. Options include:

1. PDF
2. Image (PNG)
3. HTML

#### Rehost Media

Choose to automatically re-host any third party images in the final output.

#### Page Size & Orientation

Select the page size for your generated asset:&#x20;

1. Letter&#x20;
2. A4
3. Full Page&#x20;
4. Custom Dimensions (if selected you will supply the height and width in pixels)

Select the orientation type for your document:

1. Portrait&#x20;
2. Lanscape&#x20;

## Generated Asset Examples

* Instagram Carousels&#x20;
* Canva-like social media posts&#x20;
* Financial Reports&#x20;
* Business Presentations&#x20;
* Resumes&#x20;

## Inserting Variables to your HTML Document&#x20;

Once you've added in your HTML template to the source document environment, you can add variables using Handlebars notation.

### Single Value Variables&#x20;

Single-value variables hold one piece of data (**such as a title, URL, or short text**) in your HTML template. You add them by writing your <mark style="color:red;">`{{variableName}}`</mark>, and when the template runs, it will be replaced with its actual value.

#### Example:

```html
<!-- Page title -->
<h1>{{page.title}}</h1>

<!-- Subtitle -->
<h2>{{page.subtitle}}</h2>

<!-- Image source -->
<img src="{{page.imageURL}}" alt="{{page.imageAltText}}" />
```

### Looping Arrays

When your JSON contains arrays you can use the <mark style="color:red;">`each`</mark> helper to loop through a list of sections in your array.&#x20;

#### Example:

```html
{{#each page.sections}}
  <section>
    <h3>{{this.header}}</h3>
    <p>{{this.body}}</p>
  </section>
{{/each}}
```

### Conditional Rendering

You can use <mark style="color:red;">`if-else`</mark> to render a block of HTML when a value meets a certain condition.&#x20;

#### Example:&#x20;

```html
{{#if page.featured}}
  <div class="featured-banner">
    Featured article: {{page.title}}
  </div>
{{/if}}
```

For more information on Handelbars notation, please review our article on [Using Handlebars Templating.](broken-reference)




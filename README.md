# Datadog Take Home Test

## Technologies

Per the stated requirements, this uses the following:

- Hugo static site builder
- Bootstrap 4
- SASS/SCSS
- git

## Assumptions and Decisions

Given the necessarily limited nature of communication regarding functionality
requirements, I did make some assumptions and opinionated decisions as part of
the build process.

In the actual team environment, a number of things could change how I approach
some of these issues:

- Visibility into the actual website content (how it is managed and formatted)
- Team preferences and best practices for various aspects of the build
- Actual Hugo usage and configuration in the company environment

So with that in mind, here are some decisions I made for this build:

1. I initially toyed with a pixel-perfect width sidebar, but spent too much time fighting with bootstrap. The final result is more fluid in width, but plays nicely with bootstrap. This also required adjusting the width of the bootstrap container variable for xl. Container-fluid would expand too far on larger screen widths.

1. While this is a single page, I did incorporate some additional page stubs so that I could use the actual Hugo Menu function to generate the navigation.

1. I put the content for the page in a markdown file with YAML front matter, as this is a very familiar format to me. If the team approaches this differently, I'm happy to adjust. Hugo has a lot of flexibility in this area.

1. The main content of this page is a masonry style layout, and I chose to use a CSS-only approach. In some cases, a layout like this would be easily done with a simple column-based approach, but given the nature of the content blocks and how they are laid out, a row-based approach was clearly the way to go (while maintaining a reasonable data storage format). Of course this decision could be affected by the actual data format.

   The downside of the particular CSS Grid approach I used is that dimensions are not 100% identical to the design. On the actual team, I would make sure that an implementation decision like this was acceptable to the design team and anyone else involved.

1. For most spacing and typography, I relied on modifying bootstrap variables (and adding some of my own). This means that I also may have deviated slightly from a pixel-perfect design in some areas, due to erring on the side of using existing spacing and typography variables instead of one-off styles.

   Opinion: Pixel-perfect reproduction will suffer somewhat with responsive design anyway, so while I strive for pixel-perfect reproduction at the sizes included in the design, taking a static design into a fluid medium will necessitate some departures from that no matter what. I believe I have an eye for design that helps me make these changes while remaining true to the intent. As I said earlier, I would consult with all interested parties as opposed to making unilateral design changes when working on the team.

1. This is less a decision and more of a roadblock. You may notice the styling of the prices isn't quite right. It depends on having equal height numbers, which is a feature of the font we are using. However, no matter how hard I tried, I was unable to actually enable the features. My guess is this is because I only have access to a test version of the font instead of the actual purchased version.

1. The carousel section is really more like two separate carousels that work together, so that's how I built it. The design of the image portion doesn't really work with the bootstrap carousel that's already available to us in that framework (sadly), so I pulled out a lightweight carousel that gives a lot more design flexibility, Owl Carousel.

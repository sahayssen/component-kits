<!--
@component
This is your page!
-->
<script>
  // Import all the news furniture components
  import ArticleHeader from '$lib/components/ArticleHeader.svelte';
  import ArticleBody from '$lib/components/ArticleBody.svelte';
  import Image from '$lib/components/Image.svelte';
  import RelatedLinks from '$lib/components/RelatedLinks.svelte';
  import Input from '$lib/components/Input.svelte';
  import WriterBio from '$lib/components/WriterBio.svelte';
  import Dropdown from '$lib/components/Dropdown.svelte';
  import UploadVideo from '$lib/components/UploadVideo.svelte';

  // Article metadata
  let headline = 'Become a force for good. Join our next class.';
  let byline = 'NYCity News Service';
  let pubDate = '2026-01-31';

  // Related stories
  const relatedStories = [
    { headline: 'How America\'s top news organizations escape rigid publishing systems to design beautiful data-driven stories on deadline.', href: 'https://palewi.re/docs/coding-the-news/' },
    { headline: 'How to install, configure and use Visual Studio Code, GitHub and Copilot', href: 'https://palewi.re/docs/coding-the-news/scripts/week-1/' },
    { headline: "How to publish a website with Node.JS and GitHub Actions", href:"https://palewi.re/docs/coding-the-news/scripts/week-2/"},
  ];
</script>

<!-- This sets the page title in the browser tab -->
<svelte:head>
  <title>{headline} | NYCity News Service</title>
  <meta name="description" content="At the Craig Newmark Graduate School of Journalism at the City University of New York, change is in our DNA. That comes of being born in 2006, as the digital revolution was transforming our profession in ways none of us could have imagined." />
</svelte:head>

<!-- Your page content goes here -->
<div class="container">
  
  <!-- Article Header: Headline, byline, and publication date -->
  <ArticleHeader
    {headline}
    {byline}
    {pubDate}
  />

  <!-- Lead Image: Animated gif of students at the journalism school -->
  <Image
    src="/funny.JPG"
    alt="The Craig Newmark Graduate School of Journalism is at 219 West 40th Street in Midtown Manhattan."
    caption="The Craig Newmark Graduate School of Journalism is at 219 West 40th Street in Midtown Manhattan."
    credit="Craig Newmark Graduate School of Journalism"
  />
 
  <!-- Article Body: The main story text with proper typography -->
  <ArticleBody>
    <p>
      At the Craig Newmark Graduate School of Journalism at the City University of New York, change is in our DNA. That comes of being born in 2006, as the digital revolution was transforming our profession in ways none of us could have imagined.
    </p>

    <p>
      We fashioned a school to teach the latest storytelling, entrepreneurial, and technological skills alongside reporting, writing, and ethics. Beyond that, we’ve crafted a culture that spurns complacency, that isn’t afraid to pivot before the ground under us shifts.
    </p>

  <UploadVideo url="https://www.youtube.com/watch?v=TR3c65lrVzo" />

    <p>
      Our mission is to serve the public interest – by training new journalists from varied economic, racial, and cultural backgrounds who will bring much-needed diversity to newsrooms, by helping mid-career journalists retool their skills, and by partnering with other media organizations to find new paths to excellence.
    </p>

    <p>
      Our low tuition rates, along with the added backing of private donors, allow candidates for our master’s degrees in journalism and engagement journalism to receive a world-class education at an affordable price. We also offer a unique bilingual master’s in journalism for students fluent in English and Spanish.
    </p>

    <p>
      Our three media centers provide research, training, thought leadership, industry meet-ups, and financial support for quality journalistic work.
    </p>
<Dropdown
  title="Frequently Asked Questions"
  question="How long do bats live?"
  answer="Most bats live less than 20 years in the wild, but six species can live more than 30 years! 

When a baby bat is born, it is blind and virtually helpless. They are totally reliant on their mother until they are about five weeks old, at which point they can begin flying and hunting. Some species reach full size as quickly as two months.

Since baby bats are completely reliant on their mother and have little to no capacity for self-preservation, many of them die from accidents while flying or falls from high nesting places. Many bats do not live to maturity.

Once bats mature, though, their mortality rate drops significantly. Bats have few natural predators and can live a very long time; although most bat species live less than 20 years in the wild, scientists have identified six species that can live in excess of 30 years. In 2006, one tiny bat from Siberia reached the ripe old age of 41—that’s the average life expectancy of an American, circa 1885!

Some bats return to the safe roost year after year. So if you have bats in your attic, it might turn into a 30 year problem"
  />
    <p>
      We also offer a robust professional education program through regular evening and weekend workshops. And we support in-depth reporting projects of professional journalists through fellowship grants.
    </p>

    <p>
      Classes are led by accomplished full-time faculty and adjuncts, who tap their networks to help students and graduates find internships, freelance opportunities and — the ultimate prize — jobs.
    </p>

    <p>
      At a time when our profession is reeling from financial pressures and lack of trust, the Newmark Graduate School of Journalism is committed to producing the next generation of skilled, ethically minded, and diverse journalists.
    </p>

    <p>
      We invite you to be part of our world.
    </p>
  </ArticleBody>

  <WriterBio
  link="/Craig.webp"
  author="Craig Newmark"
  bio="Craig Alexander Newmark is an American internet entrepreneur and philanthropist best known as the founder of the classifieds website Craigslist. Before founding Craigslist, he worked as a computer programmer for IBM, Bank of America, and Charles Schwab.'"
  />

  <!-- Related Stories: Links to other articles -->
  <RelatedLinks
    title="Related Stories"
    links={relatedStories}
  />
<Input
name="Leave a comment"
num1="0"
num2="100"
num3="100"
/>
</div>

<style>
  /* Styles here only apply to this page */
  .container {
    padding: var(--spacing-lg) var(--spacing-md);
  }
</style>
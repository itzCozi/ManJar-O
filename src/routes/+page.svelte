<script lang="ts">
  import PageLayout from "$lib/layout/PageLayout.svelte";
  import Paragraph from "$lib/type/Paragraph.svelte";
  import BigButton from "$lib/buttons/BigButton.svelte";
  import ListItem from "$lib/layout/ListItem.svelte";

  const birthDate = new Date(2008, 9, 20);
  function calculateAge(d: Date) {
    const today = new Date();
    let age = today.getFullYear() - d.getFullYear();
    const m = today.getMonth() - d.getMonth();
    if (m < 0 || (m === 0 && today.getDate() < d.getDate())) age--;
    return age;
  }
  $: age = calculateAge(birthDate);
</script>

<svelte:head>
  <title>JARBREAKER</title>
  <meta name="description" content={`JARBREAKER (formerly ManJar-O) is a ${age}-year-old Charlotte, NC-based software developer and bedroom DJ crafting bold new sounds and tools at the intersection of music and technology.`} />
  <link rel="canonical" href="https://jarbreaker.cc/" />
  <meta name="robots" content="index, follow, max-image-preview:large, max-snippet:-1, max-video-preview:-1" />

  <meta property="og:title" content="JARBREAKER" />
  <meta property="og:description" content={`Charlotte, NC-based ${age}-year-old software developer and bedroom DJ crafting bold new sounds and tools at the intersection of music and technology.`} />
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://jarbreaker.cc/" />
  <meta property="og:image" content="https://jarbreaker.cc/logo.png" />
  <meta property="og:image:alt" content="JARBREAKER logo" />
  <meta property="og:site_name" content="JARBREAKER" />
  <meta property="og:locale" content="en_US" />

  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:title" content="JARBREAKER" />
  <meta name="twitter:description" content={`Charlotte, NC-based ${age}-year-old software developer and bedroom DJ crafting bold new sounds and tools at the intersection of music and technology.`} />
  <meta name="twitter:image" content="https://jarbreaker.cc/logo.png" />
  <meta name="twitter:url" content="https://jarbreaker.cc/" />

  <script type="application/ld+json">
    {
      "@context": "https://schema.org",
      "@type": "Person",
      "name": "JARBREAKER",
      "alternateName": "ManJar-O",
      "givenName": "Cooper",
      "familyName": "Ransom",
      "url": "https://jarbreaker.cc/",
      "image": "https://jarbreaker.cc/logo.png",
      "jobTitle": ["DJ", "Software Developer"],
      "birthDate": "2008-10-20",
      "address": {
        "@type": "PostalAddress",
        "addressLocality": "Charlotte",
        "addressRegion": "NC",
        "addressCountry": "US"
      },
      "sameAs": [
        "https://soundcloud.com/jarbreaker",
        "https://www.instagram.com/jarbreakerdj/"
      ],
      "email": "mailto:dev@wyzie.ru",
      "telephone": "+1-980-297-9605"
    }
  </script>
</svelte:head>

<PageLayout>
  <h1 class="sr-only">JARBREAKER from Charlotte, North Carolina</h1>
  <img src="/logo.png" alt="JARBREAKER" class="w-36 h-36 mx-auto mb-4 object-cover" />

  <Paragraph className="mt-3 mb-4">
    JARBREAKER (formerly ManJar-O), aka Cooper Ransom, is a {age}-year-old software developer and bedroom DJ from Charlotte, North Carolina. Having learned software development in his early teens, he channels his passion for creation into crafting bold new sounds from existing content. His journey fuses technology with vibrant artistic expression and a love for people and music.
  </Paragraph>

  <div class="border border-mono-divider mb-4 p-1.5">
    <ListItem
      href="https://soundcloud.com/jarbreaker"
      text="SoundCloud" />
    <ListItem
      href="https://www.instagram.com/jarbreakerdj/"
      text="Instagram" />
  </div>

  <div class="flex flex-row gap-2">
    <BigButton
      title="Email"
      onClick={() => window.open("mailto:dev@wyzie.ru")}
      className="w-full py-2">
      dev@wyzie.ru
    </BigButton>

    <BigButton
      title="Phone number"
      onClick={() => window.open("tel:9802979605")}
      className="w-full py-2">
      (980)-297-9605
    </BigButton>
  </div>
</PageLayout>

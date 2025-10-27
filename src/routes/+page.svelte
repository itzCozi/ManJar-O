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

<PageLayout>
  <img src="/logo.png" alt="JARBREAKER" class="w-36 h-36 mx-auto mb-4 object-cover" />

  <Paragraph className="mt-3 mb-4">
    JARBREAKER, aka Cooper Ransom, is a {age}-year-old software developer and bedroom DJ from Charlotte, North Carolina. Having learned software development in his early teens, he channels his passion
    for creation into making new bold sounds from existing content. His journey fuses technology with a vibrant artistic expression, and a love for all things "people" and music.
  </Paragraph>

  <div class="border border-mono-divider mb-4 p-1.5">
    <ListItem
      href="https://soundcloud.com/JARBREAKER"
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

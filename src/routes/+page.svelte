<script>
    import Header from "cmd-midterm-components/components/Header.svelte"
    import Link  from 'cmd-midterm-components/components/Link.svelte'
    import Mainhero from 'cmd-midterm-components/components/Mainhero.svelte';
    import Footer from "cmd-midterm-components/components/Footer.svelte"
    import  Cursor  from "cmd-midterm-components/components/Cursor.svelte";
    import Intro from "$lib/components/Intro.svelte";
    import Standard from "$lib/components/Standard.svelte";
	import StandardChapter from "$lib/components/StandardChapter.svelte";
	import StandardSection from "$lib/components/StandardSection.svelte";
    import  Carousel from "cmd-midterm-components/components/Carousel.svelte"
    import  ChapterContent  from "cmd-midterm-components/components/ChapterContent.svelte"
    export let data;
    export let page;

</script>

<Header
<Header title="CMD Mid-term" isYellow>
    <Link type="li" href="./beoogde-leerresultaten">Beoogde leerresultaten</Link>
    <Link type="li" href="./onderwijsleeromgeving">Onderwijsleeromgeving</Link>
    <Link type="li" href="./toetsing">Toetsing</Link>
    <Link type="li" href="./gerealiseerde-leerresultaten">gerealiseerde-leerresultaten</Link>
</Header>
<Mainhero
title="Communcation and Multimedia Design"
imageAlt="Woman with laptop"
hasButtons="true"/>
<Intro introductionTitle={"Midterm"} introduction={data.page.introduction} />

<StandardSection>
	{#each data.standards as standard}
		<Standard
			standardUID={`/${standard?.uid}`}
			standardTitle={`${standard?.standardnumber}.0 ${standard.title}`}
		>
			{#each standard.chapters as chapter, i}
				<StandardChapter
					chapterTitle={`${standard.standardnumber}.0${i + 1} ${
						chapter.data.title
					}`}
				/>
			{/each}
		</Standard>
	{/each}
</StandardSection>


<Footer/>

<style>


</style>
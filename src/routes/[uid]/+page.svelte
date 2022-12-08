<script>
import Header from "cmd-midterm-components/components/Header.svelte"
import Link  from 'cmd-midterm-components/components/Link.svelte'
	import ChapterSection from "$lib/components/DetailComponents/ChapterSection.svelte";
	import ChapterContentleft from "$lib/components/DetailComponents/ChapterContentleft.svelte";
	import ChapterContentright from "$lib/components/DetailComponents/ChapterContentright.svelte";
	import StandardHero from "$lib/components/DetailComponents/StandardHero.svelte";
    import Footer from "cmd-midterm-components/components/Footer.svelte"
	import Backtotop from "../../lib/components/Backtotop.svelte";


	export let data;
</script>

<Header title="CMD Mid-term" isYellow
>
    <Link type="li" href="./beoogde-leerresultaten">Beoogde leerresultaten</Link>
    <Link type="li" href="./onderwijsleeromgeving">Onderwijsleeromgeving</Link>
    <Link type="li" href="./toetsing">Toetsing</Link>
    <Link type="li" href="./gerealiseerde-leerresultaten">gerealiseerde-leerresultaten</Link>
</Header>
<StandardHero
        standardHeaderTitle={data.standard.data.title}
		standardHeaderIntroduction={data.standard.data.introduction}
		standardNumber={data.standard.data.standardnumber}
/> 

{#each data.standard.data.chapters as chapter, i}
		<ChapterSection
			chapterTitle={chapter.data.title}
			chapterNumber={`${data.standard.data.standardnumber}.${i + 1}`}
			chapterUID={chapter.uid}
		>
			<ChapterContentleft contentLeft={chapter.data.contentleft} />
			<ChapterContentright contentRight={chapter.data.contentright} />
		</ChapterSection>
	{/each}
	<Footer/>
	<Backtotop/>

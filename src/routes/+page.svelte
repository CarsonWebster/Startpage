<script lang="ts">
	interface link {
		name: string;
		url: string;
	}
	interface linkSection {
		[key: string]: link[];
	}

	let name: string = 'Carson';
	// let LinkSections = ['Work', 'Practice', 'Fun'];
	let LinkSections: linkSection[] = [
		{
			Grind: [
				{ name: 'HackerRank', url: 'https://www.hackerrank.com' },
				{ name: 'HackTheBoxAcademy', url: 'https://academy.hackthebox.com/dashboard' },
				{ name: 'HackerOne', url: 'https://www.hackerone.com/' }
			]
		},
		{
			Work: [
				{ name: 'LinkedIn', url: 'https://www.linkedin.com/' },
				{ name: 'Indeed', url: 'https://www.google.com' },
				{ name: 'Handshake', url: 'https://ucsc.joinhandshake.com/stu/postings' }
			]
		},
		{
			Media: [
				{ name: 'Youtube', url: 'https://www.youtube.com' },
				{ name: 'Netflix', url: 'https://www.netflix.com' },
				{ name: 'Reddit', url: 'https://www.reddit.com' }
			]
		}
	];
</script>

<div class="container h-full mx-auto">
	<div class="space-y-5">
		<h1 class="h1 mt-20 text-center text-pink-500">Welcome,<br/>{name}</h1>
		<hr class="!border-t-4" />

		<div class="flex justify-between">
			{#each LinkSections as linkSection}
				{#each Object.entries(linkSection) as [groupName, links]}
					<div class="mx-8">
						<p class=" text-pink-800 text-center font-semibold text-base">{groupName}</p>
						<hr class="!border-dashed" />
						{#each links as link}
							<div class="text-center text-pink-300">
								<a href={link.url}>{link.name}</a>
							</div>
						{/each}
					</div>
				{/each}
			{/each}
		</div>
	</div>
</div>

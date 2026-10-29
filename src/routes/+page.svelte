<script>
	const name = 'Junayeed'.split('');

	const stats = [
		'3 nodes',
		'56 services',
		'29 domains',
		'~3,100 signed commits',
		'400k+ installs',
		'every commit SSH-signed',
		'boring tech, audited hard'
	];

	const beliefs = [
		'Own the metal.',
		'The source of truth is a git repo.',
		"If it isn't rendered, reviewed and reproducible, it isn't done.",
		'Boring technology, audited hard, beats fashionable technology trusted blindly.'
	];

	const stack = [
		{ name: 'Linux', href: 'https://kernel.org' },
		{ name: 'Salt', href: 'https://saltproject.io' },
		{ name: 'GitLab CI', href: 'https://docs.gitlab.com/ee/ci/' },
		{ name: 'Forgejo', href: 'https://forgejo.org' },
		{ name: 'Git', href: 'https://git-scm.com' },
		{ name: 'Podman', href: 'https://podman.io' },
		{ name: 'Caddy', href: 'https://caddyserver.com' },
		{ name: 'Ruby', href: 'https://www.ruby-lang.org' },
		{ name: 'PostgreSQL', href: 'https://www.postgresql.org' }
	];

	const links = [
		{ label: 'github', handle: '/fakeid30', href: 'https://github.com/fakeid30', external: true },
		{
			label: 'linkedin',
			handle: '/junayeed-ahnaf',
			href: 'https://www.linkedin.com/in/junayeed-ahnaf',
			external: true
		},
		{ label: 'mail', handle: '@protonmail', href: 'mailto:junayeed@protonmail.com', external: false }
	];
</script>

<svelte:head>
	<title>Junayeed</title>
	<meta name="description" content="Junayeed: infrastructure, release planning, and plain-text systems." />
</svelte:head>

<div class="glow" aria-hidden="true"></div>

<main class="wrap">
	<header>
		<p class="prompt">~ $ whoami</p>
		<h1 aria-label="Junayeed">
			{#each name as letter, i (i)}<span aria-hidden="true" style="--i: {i}">{letter}</span>{/each}<span
				class="cursor"
				aria-hidden="true"
			></span>
		</h1>
		<p class="sub">
			Dhaka, Bangladesh (UTC+6). I run infrastructure and plan software releases.
		</p>
	</header>
</main>

<div class="ticker" aria-hidden="true">
	<div class="ticker-track">
		{#each { length: 6 } as _, copy (copy)}
			{#each stats as stat (copy + stat)}
				<span class="tick">{stat}<i>✦</i></span>
			{/each}
		{/each}
	</div>
</div>

<main class="wrap body">
	<section>
		<h2><span class="dollar">$</span> cat now.txt</h2>
		<p>
			Project Manager at <a href="https://happymonster.dev" target="_blank" rel="noopener noreferrer">HappyMonster</a> since
			January 2024. I lead Dev, Marketing, Content and Design for
			<a href="https://happyaddons.com" target="_blank" rel="noopener noreferrer">HappyAddons</a>, a WordPress plugin on
			400k+ sites. I own the roadmap, the releases and delivery.
		</p>
		<p>
			I came up through QA (2021) and DevOps (2022–23) in the same company. When I plan a roadmap,
			I know what the work costs because I've done it.
		</p>
	</section>

	<section>
		<h2><span class="dollar">$</span> ls ~/fleet</h2>
		<p>
			I run a private fleet of three machines: claw, cyclops and eden. They run AlmaLinux with
			rootless Podman, Caddy and Salt. Together they host 56 services behind 29 domains. These
			include chat, video calls, notes, a password vault, budgeting and a status page.
		</p>
		<p>
			Forgejo, self-hosted, is the source of truth. Seven repos mirror out to GitLab and GitHub.
			Every push triggers a CI job that rebuilds a server from its Salt states. If the rebuild
			fails, the state isn't finished. Backups are tested weekly, and drift and certificate checks
			are reported automatically. All ~3,100 commits are SSH-signed.
		</p>
		<p>
			I also build small decision tools in Ruby: models and a self-hosted engine that turn messy
			data into an answer you can defend. My agents and scripts are Ruby too.
		</p>
	</section>

	<section>
		<h2><span class="dollar">$</span> cat beliefs.md</h2>
		<ol class="beliefs">
			{#each beliefs as belief, i (i)}
				<li>
					<span class="num">{String(i + 1).padStart(2, '0')}</span>
					<span class="belief">{belief}</span>
				</li>
			{/each}
		</ol>
	</section>

	<section>
		<h2><span class="dollar">$</span> stack --list</h2>
		<div class="stack">
			{#each stack as tool (tool.name)}
				<a href={tool.href} target="_blank" rel="noopener noreferrer">{tool.name}</a>
			{/each}
		</div>
	</section>

	<section>
		<h2><span class="dollar">$</span> ping elsewhere</h2>
		<ul class="links">
			{#each links as link (link.label)}
				<li>
					<a
						href={link.href}
						target={link.external ? '_blank' : undefined}
						rel={link.external ? 'noopener noreferrer' : undefined}
					>
						<span class="label">{link.label}</span>
						<span class="handle">{link.handle}</span>
						<span class="arrow" aria-hidden="true">→</span>
					</a>
				</li>
			{/each}
		</ul>
	</section>

	<footer>
		<p>
			Built with SvelteKit + Bun. Compiled to static HTML.
			<a href="https://github.com/fakeid30/fakeid30.github.io" target="_blank" rel="noopener noreferrer">view source</a>
		</p>
	</footer>
</main>

<style>
	.glow {
		position: absolute;
		inset: 0 0 auto 0;
		height: 34rem;
		background: radial-gradient(
			ellipse 60% 55% at 50% 0%,
			var(--accent-dim),
			transparent 70%
		);
		pointer-events: none;
		z-index: -1;
	}

	.wrap {
		max-width: 44rem;
		margin: 0 auto;
		padding: 0 1.5rem;
	}

	header {
		padding: 6rem 0 3rem;
	}

	.prompt {
		font-family: var(--mono);
		font-size: 0.85rem;
		color: var(--dim);
		margin-bottom: 1rem;
	}

	h1 {
		font-size: clamp(3.6rem, 13vw, 8.5rem);
		font-weight: 800;
		letter-spacing: -0.04em;
		line-height: 0.95;
		display: flex;
		align-items: baseline;
	}

	h1 span {
		display: inline-block;
		transition:
			color 0.15s ease,
			transform 0.25s cubic-bezier(0.2, 0.9, 0.3, 1.4);
	}

	h1 span:hover {
		color: var(--accent);
		transform: translateY(-0.08em) skewX(-6deg);
	}

	.cursor {
		width: 0.14em;
		height: 0.82em;
		background: var(--accent);
		margin-left: 0.06em;
		align-self: center;
	}

	.sub {
		margin-top: 1.4rem;
		color: var(--dim);
		font-size: 1.25rem;
		max-width: 30rem;
	}

	.ticker {
		border-top: 1px solid var(--line);
		border-bottom: 1px solid var(--line);
		overflow: hidden;
		white-space: nowrap;
		padding: 0.65rem 0;
	}

	.ticker-track {
		display: flex;
		width: max-content;
	}

	.tick {
		font-family: var(--mono);
		font-size: 0.8rem;
		text-transform: uppercase;
		letter-spacing: 0.14em;
		color: var(--dim);
	}

	.tick i {
		font-style: normal;
		color: var(--accent);
		margin-left: 1.5rem;
	}

	.body {
		padding-bottom: 1rem;
	}

	section {
		padding: 2.5rem 0;
		border-bottom: 1px solid var(--line);
	}

	h2 {
		font-family: var(--mono);
		font-size: 0.85rem;
		font-weight: 500;
		color: var(--fg);
		margin-bottom: 1.4rem;
	}

	.dollar {
		color: var(--accent);
	}

	section p {
		max-width: 38rem;
	}

	section p + p {
		margin-top: 0.9rem;
	}

	section p a {
		color: var(--accent);
		text-decoration-color: transparent;
		text-underline-offset: 3px;
		transition: text-decoration-color 0.2s ease;
	}

	section p a:hover {
		text-decoration-color: var(--accent);
	}

	.beliefs {
		list-style: none;
	}

	.beliefs li {
		display: flex;
		gap: 1.2rem;
		padding: 0.8rem 0;
		font-size: 1.15rem;
		line-height: 1.5;
		border-bottom: 1px dashed transparent;
		transition:
			padding-left 0.25s ease,
			color 0.25s ease;
	}

	.beliefs li:hover {
		padding-left: 0.6rem;
		color: var(--accent);
	}

	.num {
		font-family: var(--mono);
		font-size: 0.8rem;
		color: var(--accent);
		padding-top: 0.35rem;
		flex-shrink: 0;
	}

	.belief {
		max-width: 34rem;
	}

	.stack {
		display: flex;
		flex-wrap: wrap;
		gap: 0.55rem;
	}

	.stack a {
		font-family: var(--mono);
		font-size: 0.85rem;
		padding: 0.35rem 0.9rem;
		border: 1px solid var(--line);
		border-radius: 999px;
		color: var(--dim);
		text-decoration: none;
		cursor: pointer;
		transition:
			background 0.15s ease,
			color 0.15s ease,
			border-color 0.15s ease,
			transform 0.15s ease;
	}

	.stack a:hover,
	.stack a:focus-visible {
		background: var(--accent);
		border-color: var(--accent);
		color: var(--bg);
		transform: rotate(-2deg) scale(1.05);
	}

	.links {
		list-style: none;
		display: grid;
		gap: 0.4rem;
	}

	.links a {
		display: flex;
		gap: 1rem;
		align-items: baseline;
		color: var(--fg);
		text-decoration: none;
		width: fit-content;
		font-family: var(--mono);
		font-size: 1.05rem;
		padding: 0.3rem 0;
	}

	.links .handle {
		color: var(--dim);
	}

	.links .arrow {
		color: var(--accent);
		opacity: 0;
		transform: translateX(-0.5rem);
		transition:
			opacity 0.2s ease,
			transform 0.2s ease;
	}

	.links a:hover .arrow {
		opacity: 1;
		transform: translateX(0);
	}

	.links a:hover .label {
		color: var(--accent);
	}

	footer {
		padding: 2.5rem 0 4rem;
		color: var(--dim);
		font-size: 0.85rem;
		font-family: var(--mono);
	}

	footer a {
		color: var(--dim);
		text-underline-offset: 3px;
	}

	footer a:hover {
		color: var(--accent);
	}

	@media (prefers-reduced-motion: no-preference) {
		.cursor {
			animation: blink 1.1s steps(1) infinite;
		}

		.ticker-track {
			animation: scroll 28s linear infinite;
		}

		.ticker:hover .ticker-track {
			animation-play-state: paused;
		}

		@keyframes blink {
			50% {
				opacity: 0;
			}
		}

		@keyframes scroll {
			to {
				transform: translateX(-50%);
			}
		}
	}

	@media (max-width: 640px) {
		header {
			padding: 4rem 0 2.5rem;
		}
	}
</style>

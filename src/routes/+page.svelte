<main class="wrap">
	<header>
		<h1>Junayeed</h1>
		<p>Dhaka, Bangladesh (UTC+6). I run infrastructure and plan software releases.</p>
	</header>

	<section>
		<h2>Now</h2>
		<p>
			Project Manager at <a href="https://happymonsters.co" rel="noopener">HappyMonster</a> since
			January 2024. I lead Dev, Marketing, Content and Design for
			<a href="https://happyaddons.com" rel="noopener">HappyAddons</a>, a WordPress plugin on
			400k+ sites. I own the roadmap, the releases and delivery.
		</p>
		<p>
			I came up through QA (2021) and DevOps (2022–23) in the same company. When I plan a roadmap,
			I know what the work costs because I've done it.
		</p>
	</section>

	<section>
		<h2>On the side</h2>
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
		<h2>Beliefs</h2>
		<ul class="beliefs">
			<li>Own the metal.</li>
			<li>The source of truth is a git repo.</li>
			<li>If it isn't rendered, reviewed and reproducible, it isn't done.</li>
			<li>Boring technology, audited hard, beats fashionable technology trusted blindly.</li>
		</ul>
	</section>

	<section>
		<h2>Stack</h2>
		<div class="stack">
			<span>Linux</span>
			<span>Salt</span>
			<span>GitLab CI</span>
			<span>Forgejo</span>
			<span>Git</span>
			<span>Podman</span>
			<span>Caddy</span>
			<span>Ruby</span>
			<span>PostgreSQL</span>
		</div>
	</section>

	<section>
		<h2>Elsewhere</h2>
		<ul class="links">
			<li>
				<a href="https://github.com/fakeid30" rel="noopener">github<span>/fakeid30</span></a>
			</li>
			<li>
				<a href="https://www.linkedin.com/in/junayeed-ahnaf" rel="noopener"
					>linkedin<span>/junayeed-ahnaf</span></a
				>
			</li>
			<li>
				<a href="mailto:junayeed@protonmail.com">mail<span>@protonmail</span></a>
			</li>
		</ul>
	</section>

	<footer>
		<p>Built with SvelteKit, compiled to static HTML. No runtime.</p>
	</footer>
</main>

<style>
	.wrap {
		max-width: 44rem;
		margin: 0 auto;
		padding: 0 1.5rem;
	}

	header {
		padding: 7rem 0 3rem;
	}

	header h1 {
		font-size: clamp(2.4rem, 7vw, 3.6rem);
		font-weight: 700;
		letter-spacing: -0.03em;
		line-height: 1.1;
	}

	header p {
		margin-top: 1.2rem;
		color: var(--dim);
		font-size: 1.25rem;
		max-width: 30rem;
	}

	section {
		padding: 2.5rem 0;
		border-top: 1px solid var(--line);
	}

	h2 {
		font-family: var(--mono);
		font-size: 0.78rem;
		font-weight: 500;
		text-transform: uppercase;
		letter-spacing: 0.18em;
		color: var(--dim);
		margin-bottom: 1.4rem;
	}

	section p {
		max-width: 38rem;
	}

	section p + p {
		margin-top: 0.9rem;
	}

	section a {
		color: var(--fg);
		text-decoration-color: var(--line);
		text-underline-offset: 3px;
	}

	section a:hover {
		color: var(--accent);
	}

	.beliefs {
		list-style: none;
	}

	.beliefs li {
		display: flex;
		gap: 1rem;
		padding: 0.55rem 0;
	}

	.beliefs li::before {
		content: '→';
		color: var(--accent);
		font-family: var(--mono);
		flex-shrink: 0;
	}

	.stack {
		display: flex;
		flex-wrap: wrap;
		gap: 0.55rem;
	}

	.stack span {
		font-family: var(--mono);
		font-size: 0.85rem;
		padding: 0.32rem 0.85rem;
		border: 1px solid var(--line);
		border-radius: 999px;
		color: var(--dim);
	}

	.links {
		list-style: none;
		display: grid;
		gap: 0.7rem;
	}

	.links a {
		display: flex;
		gap: 1rem;
		align-items: baseline;
		color: var(--fg);
		text-decoration: none;
		width: fit-content;
		font-family: var(--mono);
		font-size: 0.95rem;
	}

	.links a span {
		color: var(--dim);
	}

	.links a:hover {
		color: var(--accent);
	}

	footer {
		padding: 3rem 0 4rem;
		border-top: 1px solid var(--line);
		color: var(--dim);
		font-size: 0.85rem;
		font-family: var(--mono);
	}

	@media (prefers-reduced-motion: no-preference) {
		header h1,
		header p {
			animation: rise 0.7s ease both;
		}

		header p {
			animation-delay: 0.12s;
		}

		@keyframes rise {
			from {
				opacity: 0;
				transform: translateY(10px);
			}
		}
	}
</style>

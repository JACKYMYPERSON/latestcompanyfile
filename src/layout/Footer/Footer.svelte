<script lang="ts">
	import { defaultI18nValues, externalLink, PageSection } from "$lib";
	import { Button, IconButton } from "fluent-svelte";
	import { links } from "$data/links";
	import { _ } from "svelte-i18n";
	import Github from "./icons/github.svg?raw";
	import Discord from "./icons/discord.svg?raw";

	const contributors = [
		{
			name: "github",
			link: "https://github.com/Tropix126/",
		},
		{
			name: "微信",
			link: "https://www.theonlytails.com/",
		},
		{
			name: "qq",
			link: "https://github.com/chingucoding/",
		},
	];
</script>

<PageSection type="footer" id="page-footer">
	<div class="column">
		<a class="logo" href="/">
			<picture> </picture>
		</a>
		<div class="social-links">
			<IconButton
				href="https://github.com/JACKYMYPERSON?tab=repositories"
				title="作者GitHub"
				aria-label="GitHub repository"
				{...externalLink}
			>
				{@html Github}
			</IconButton>
		</div>
		<p>Copyright©2024 mayiming</p>
		<p>Developed by 湖北省武汉市懿科星互联网有限责任公司 鄂ICP备2024037056号</p>
	</div>
	<div class="column">
		<p>关于产品</p>
		<Button variant="hyperlink" href="/">
			{$_("首页", defaultI18nValues)}
		</Button>
		<Button variant="hyperlink" href="/docs">
			{$_("文档", defaultI18nValues)}
		</Button>
		<Button variant="hyperlink" href="/blog">
			{$_("下载", defaultI18nValues)}
		</Button>
	</div>
	<div class="column">
		<p>支持与服务</p>
		<Button
			variant="hyperlink"
			{...externalLink}
			href="https://github.com/{links.github.owner}/{links.github
				.repo}/issues/new/choose"
		>
			{$_("支持", defaultI18nValues)}
		</Button>

		<Button variant="hyperlink" href="/docs/contributing/code-style">
			{$_("会员", defaultI18nValues)}
		</Button>

		<Button
			{...externalLink}
			href="https://crowdin.com/project/files-app"
			variant="hyperlink"
		>
			{$_("优惠政策", defaultI18nValues)}
		</Button>
	</div>
	<div class="column">
		<p>联系我们</p>
		{#each contributors as contributor}
			<Button variant="hyperlink" href={contributor.link} {...externalLink}>
				{contributor.name}
			</Button>
		{/each}
	</div>
</PageSection>

<style lang="scss">
	@use "./Footer";
</style>

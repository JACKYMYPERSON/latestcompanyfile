<script lang="ts">
	import { defaultI18nValues, externalLink, PageSection } from "$lib";
	import { Button, IconButton } from "fluent-svelte";
	import { links } from "$data/links";
	import { _ } from "svelte-i18n";
	import Github from "./icons/github.svg?raw";
	import Discord from "./icons/discord.svg?raw";

	const contributors = [
		
		{
			name: "微信",
			link: "#",
		},
		{
			name: "qq",
			link: "#",
		},
	];
</script>

<PageSection type="footer" id="page-footer">
	<div class="column">
		<a class="logo" href="/">
			<picture> </picture>
		</a>
		
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
		
	</div>
	<div class="column">
		<p>支持与服务</p>
		<Button
			variant="hyperlink"
			{...externalLink}
			href="#"
		>
			{$_("支持", defaultI18nValues)}
		</Button>

		<Button variant="hyperlink" href="#">
			{$_("会员", defaultI18nValues)}
		</Button>

		<Button
			{...externalLink}
			href="#"
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

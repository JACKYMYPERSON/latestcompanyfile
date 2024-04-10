<script lang="ts">
	import { defaultI18nValues, HeaderChip, PageSection } from "$lib";
	import { Button } from "fluent-svelte";
	import { _ } from "svelte-i18n";
	let scrollPositionY: number;
</script>

<svelte:body on:scroll={() => (scrollPositionY = document.body.scrollTop)} />

<PageSection id="design-section">
	<HeaderChip>{$_("宠物喂养平台", defaultI18nValues)}</HeaderChip>
	<p>{$_("我们是一家专注于宠物喂养的公司", defaultI18nValues)}</p>

	<div class="design-image">
		<picture>
			<source
				media="(prefers-color-scheme: dark)"
				srcset="/screenshots/win11-dark.jpg"
			/>
			<source
				media="(prefers-color-scheme: light)"
				srcset="/screenshots/win11-dark.jpg"
			/>
			<img
				alt="Files folder list screenshot"
				class="files-screenshot"
				height="768"
				src="/screenshots/win11-dark.jpg"
				style:transform="translateY({Math.floor(scrollPositionY / +20)}px)"
				width="1024"
			/>
		</picture>
		<picture>
			<source
				media="(prefers-color-scheme: dark)"
				srcset="/screenshots/win11-dark.jpg"
			/>
			<source
				media="(prefers-color-scheme: light)"
				srcset="/screenshots/win11-light.jpg"
			/>
			<img
				alt="Windows 11 wallpaper"
				class="files-wallpaper"
				height="900"
				src="/screenshots/win11-light.jpg"
				width="1440"
			/>
		</picture>
	</div>
</PageSection>

<style lang="scss">
	@use "DesignSection";
</style>

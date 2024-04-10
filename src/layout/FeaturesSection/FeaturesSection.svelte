<script lang="ts">
	import { _ } from "svelte-i18n";

	import type { FeatureCardData } from "$data/features";
	import {
		defaultI18nValues,
		entries,
		FeatureCard,
		HeaderChip,
		PageSection,
	} from "$lib";

	import Cloud from "~icons/fluent/cloud-24-regular";
	import EyeVisible from "~icons/fluent/eye-20-regular";
	import Archive from "~icons/fluent/folder-zip-24-regular";
	import Columns from "~icons/fluent/panel-left-28-regular";
	import TabDesktop from "~icons/fluent/tab-desktop-20-regular";
	import Tag from "~icons/fluent/tag-24-regular";
	import Branch from "~icons/fluent/branch-24-regular";
	import Hash from "~icons/fluent/number-symbol-24-regular";
	import Diamond from "~icons/fluent/diamond-24-regular";
	import PanelRight from "~icons/fluent/panel-right-24-regular";

	export const featureCards = {
		tabs: {
			title: $_("快速响应", defaultI18nValues),
			description: $_("我们将会快速您的需求", defaultI18nValues),
			icon: TabDesktop,
		},
		dualPane: {
			title: $_("实时监控", defaultI18nValues),
			description: $_("您将会实时观察到实时的宠物状况", defaultI18nValues),
			icon: PanelRight,
		},
		tags: {
			title: $_("会员制度", defaultI18nValues),
			description: $_("会员将享受专有折扣", defaultI18nValues),
			icon: Tag,
		},
		columns: {
			title: $_("优良喂食", defaultI18nValues),
			description: $_("我们用的粮食都是经过精心挑选", defaultI18nValues),
			icon: Columns,
		},
		archives: {
			title: $_("经验丰富", defaultI18nValues),
			description: $_("投喂师傅经验丰富", defaultI18nValues),
			icon: Archive,
		},
		cloud: {
			title: $_("极致呵护", defaultI18nValues),
			description: $_("师傅将会细心照顾您的宠物", defaultI18nValues),
			icon: Cloud,
		},
		preview: {
			title: $_("安全防护", defaultI18nValues),
			description: $_("投喂过程中做好安全措施", defaultI18nValues),
			icon: PanelRight,
		},
		popupPreview: {
			title: $_("良好反馈"),
			description: $_("用户反馈良好", defaultI18nValues),
			icon: EyeVisible,
		},
		git: {
			title: $_("评价度高", defaultI18nValues),
			description: $_("公司各平台评价高", defaultI18nValues),
			icon: Branch,
		},
	} as const satisfies { [name: string]: FeatureCardData };
</script>

<PageSection id="features-section">
	<div class="features-section-right">
		<HeaderChip>{$_("服务")}</HeaderChip>
		<h2>{$_("支持与服务")}</h2>
		<p>{$_("我们将为您提供支持与服务", defaultI18nValues)}</p>
		<hr />
		<div class="feature-cards-container">
			{#each entries(featureCards) as [id, feature] (id)}
				<FeatureCard description={feature.description}>
					<svelte:component this={feature.icon} slot="icon" />
					{feature.title}
				</FeatureCard>
			{/each}
		</div>
	</div>
</PageSection>

<style lang="scss">
	@use "FeaturesSection";
</style>

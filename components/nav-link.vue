<script lang="ts" setup>
import type { NuxtLinkProps } from "#app";

export interface NavLinkProps
	extends Omit<NuxtLinkProps, "href" | "to">,
		Required<Pick<NuxtLinkProps, "href">> {}

const props = defineProps<NavLinkProps>();

const localePath = useLocalePath();
</script>

<template>
	<NuxtLink :external="props.external" :href="props.external ? props.href : localePath(props.href)">
		<slot />
	</NuxtLink>
</template>

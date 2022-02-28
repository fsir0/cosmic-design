<script lang="ts" setup>
interface TreeNode {
    key: string;
    title: string;
    children?: TreeNode[];
    indentStep?: string | number;
    treeIcon?: string;
    leafIcon?: string;
    extra?: string;
}

interface TreeProps {
    data: TreeNode[];
}

withDefaults(defineProps<TreeProps>(), {
    data: () => []
});

defineEmits(['expand', 'extraClick']);

function onExpand() {

}

function onExtraClick() {

}
</script>

<style>
.tree-node {
    height: 30px;
    padding-right: 3px;
    display: flex;
    align-items: center;
    font-size: 12px;
    color: #1f1f1f;
    background: #fff;
}
.tree-node:hover {
    background: #f3f4f6;
}
</style>

<template>
    <div>
        <!-- render title -->
        <!-- render children -->
        <!-- render icon -->
        <!-- render extra -->
        <template v-if="data && data.length">
            <tree v-for="treeNode in data" >

            </tree>
        </template>
        <template v-else>
            
            <slot></slot>
        </template>

        <!-- <div
            v-for="treeNode in data"
            class="tree-node"
            style={`padding-left: ${primaryIndent}rem;`}
            @click.sotp="onExpand"
        >

            {#if children && children.length}
                <div class="flex-none">
                    <Icon>{arrowStatus}</Icon>
                </div>
                {#if treeIcon}
                    <Icon small classes="mr-4">{treeIcon}</Icon>
                {/if}
            {:else if leafIcon}
                <Icon small classes="mr-4">{leafIcon}</Icon>
            {/if}

            <span class="flex-auto">{label}</span>
            {#if extraIcon}
                <div class="flex-none" on:click|stopPropagation={onClickExtra}>
                    <Icon small>{extraIcon}</Icon>
                </div>
            {/if}
        </div>
        {#if expanded && children && children.length}
            {#each children as child}
                <svelte:self
                    {extraIcon}
                    data={child}
                    primaryIndent={primaryIndent + indentStep}
                    {indentStep}
                    on:click-extra
                    on:click
                />
            {/each}
        {/if} -->
    </div>
</template>
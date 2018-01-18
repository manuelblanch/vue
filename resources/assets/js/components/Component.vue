<!DOCTYPE html>
<html lang="en">
<template>
    <div v-if="!removed" class="box" :class="[{'box-solid' : isSolid}, {'collapsed-box' : isCollapsed  }, 'box-' + color]">
        <div class="box-header" :class="{'with-border' : borderOnHeader}">
            <div class="box-title" v-if="!noTitle">
                <slot name="title"></slot>
            </div>
            <div class="box-tools pull-right" v-if="!noTitle">
                <slot name="box-tools">
                    <button v-if="isCollapsable" type="button" class="btn btn-box-tool" data-widget="collapse"><i class="fa" :class="collapseIcon"></i></button>
                    <button @click="remove()" v-if="isRemovable" type="button" class="btn btn-box-tool" data-widget="remove"><i class="fa fa-times"></i></button>
                </slot>
            </div>
        </div>
        <div class="box-body">
            <slot>Put your content here using default slot</slot>
        </div>
        <div class="box-footer" v-if="hasFooterSlot()">
            <slot name="footer">This is the footer!</slot>
        </div>
        <div class="overlay" v-if="isLoading">
            <i class="fa fa-refresh fa-spin"></i>
        </div>
    </div>
</template>
</html>

<template>
    <DocSectionText v-bind="$attrs">
        <p>Custom content can be placed inside the menuitem using the <i>item</i> templating.</p>
    </DocSectionText>
    <div class="card flex justify-content-center">
        <Breadcrumb :home="home" :model="items">
            <template #item="{ item }">
                <a :class="item.class" :href="item.url">
                    <span :class="item.icon"></span>
                </a>
            </template>
        </Breadcrumb>
    </div>
    <DocSectionCode :code="code" />
</template>

<script>
export default {
    data() {
        return {
            home: { icon: 'pi pi-home', url: 'https://primevue.org/' },
            items: [{ icon: 'pi pi-sitemap' }, { icon: 'pi pi-book' }, { icon: 'pi pi-wallet' }, { icon: 'pi pi-shopping-bag' }, { icon: 'pi pi-calculator' }],
            code: {
                basic: `
<Breadcrumb :home="home" :model="items">
    <template #item="item">
        <a :class="item.class">
            <span :class="item.icon"></span>
        </a>
    </template>
</Breadcrumb>
`,
                options: `
<template>
    <div class="card flex justify-content-center">
        <Breadcrumb :home="home" :model="items">
            <template #item="{item}">
                <a :class="item.class">
                    <span :class="item.icon"></span>
                </a>
            </template>
        </Breadcrumb>
    </div>
</template>

<script>
export default {
    data() {
        return {
            home: { icon: 'pi pi-home', url: 'https://primevue.org/' },
            items: [{ icon: 'pi pi-sitemap' }, { icon: 'pi pi-book' }, { icon: 'pi pi-wallet' }, { icon: 'pi pi-shopping-bag' }, { icon: 'pi pi-calculator' }]
        }
    }
}
<\/script>
`,
                composition: `
<template>
    <div class="card flex justify-content-center">
        <Breadcrumb :home="home" :model="items">
            <template #item="{item}">
                <a :class="item.class">
                    <span :class="item.icon"></span>
                </a>
            </template>
        </Breadcrumb>
    </div>
</template>

<script setup>
import { ref } from "vue";

const home = ref({ icon: 'pi pi-home', url: 'https://primevue.org/' });
const items = ref([{ icon: 'pi pi-sitemap' }, { icon: 'pi pi-book' }, { icon: 'pi pi-wallet' }, { icon: 'pi pi-shopping-bag' }, { icon: 'pi pi-calculator' }]);
}
<\/script>
`
            }
        };
    }
};
</script>

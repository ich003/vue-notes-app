<template>
    <div class="navbar-fixed" v-if="$route.path.includes('editor') == false">
        <nav>
            <div class="nav-wrapper black">
                <a id="navTitle" class="brand-logo left">{{ $route.name }}</a>
                <ul class="right">
                    <li>
                        <router-link class="waves-effect waves-light" to="/notes">
                            <i class="material-icons">list</i>
                        </router-link>
                    </li>
                    <li>
                        <router-link class="waves-effect waves-light" to="/archive">
                            <i class="material-icons">archive</i>
                        </router-link>
                    </li>
                    <li>
                        <router-link class="waves-effect waves-light" to="/trash">
                            <i class="material-icons">delete</i>
                        </router-link>
                    </li>
                    <li>
                        <router-link class="waves-effect waves-light" to="/config">
                            <i class="material-icons">settings</i>
                        </router-link>
                    </li>
                </ul>
            </div>
        </nav>
    </div>
</template>

<script>
export default {
    props: ['title'],
    name: 'navbar'
}
</script>

<style scoped>
#navTitle {
    padding-left: 10px;
}

.router-link-active {
    border-bottom: 4px solid black;
}
</style>

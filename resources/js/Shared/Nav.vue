<template>
  <nav>
        <ul class="flex space-x-6">
            <li>
                <NavLink href="/" :active="$page.component == 'Home'">
                    Home
                </NavLink>
            </li>
             <li>
                <NavLink href="/users" :active="$page.component == 'Users'">
                    Users
                </NavLink>
            </li>
             <li>
                <NavLink href="/settings" :active="$page.component == 'Settings'">
                    Settings
                </NavLink>
            </li>
             <li>
                <NavLink href="/logout" method="post">
                    Log Out
                </NavLink>
            </li>
            <!-- <li>
                <Link
                    href="/"
                    class="text-blue-500 hover:underline"
                    :class="{ 'font-bold underline': $page.component == 'Home' }"
                    >
                    Home
                </Link>
            </li> -->

            <!-- <li>
                <Link href="/logout" :data="{ foo: 'bar' }" method="post" as="button" class="text-blue-500 hover:underline">Log Out</Link>
            </li> -->

        </ul>
    </nav>
</template>

<script>
    import NavLink from './NavLink.vue'

    export default {
        components: {
            NavLink
        }
    }
</script>

<style>

</style>

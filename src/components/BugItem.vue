<template>
    <tr>
        <td><input type="checkbox"></td>
        <td>{{ bugDetail }}</td>
        <td><button>删除</button></td>
    </tr>
</template>

<script>
export default {
    props: ['bugDetail']
}
</script>

<style></style>
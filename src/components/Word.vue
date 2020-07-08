<template>
    <div class="row">
            <div class="col-md-8 offset-md-2 border d-flex flew-row justify-content-between align-items-center pt-2 pb-2">
                <span>{{word.english}} </span>
                <span>{{word.turkish}} </span>
            </div>
    </div>
</template>

<script>
export default {
    props : ["word"]
}
</script>
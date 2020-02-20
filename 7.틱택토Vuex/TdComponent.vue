<template>
    <td @click="onClickTd">{{cellData}}</td>
</template>

<script>
    import { mapState } from 'vuex';
    import {CHANGE_TURN, CLICK_CELL, NO_WINNER, RESET_GAME, SET_WINNER} from "./store";

    export default {
        name: "TdComponent",
        props: {
            rowIndex: Number,
            cellIndex: Number,
        },
        computed: {
            ...mapState({
                tableData: state => state.tableData,
                turn: state => state.turn,
                cellData(state) {
                    return state.tableData[this.rowIndex][this.cellIndex];
                }
            })
        },
        methods: {

        }

    }
</script>

<style scoped>

</style>
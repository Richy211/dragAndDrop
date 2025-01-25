<script setup>
import { reactive, watch } from 'vue';
import InputNew from './InputNew.vue';

let boards = reactive([
    {
        id: crypto.randomUUID(),
        name: "tablero 1",
        items: [
            {
                id:crypto.randomUUID(),
                title:"Feature de archivos",
            },
            {
                id:crypto.randomUUID(),
                title: "Resolver bug",
            },
        ],
    }
]);

//Guardar los datos en el local Storage cada vez que cambien
watch(
    () => boards,(newBoards) => {
        localStorage.setItem('boards', JSON.stringify(newBoards));        
    },
    { deep: true }
);

function handleNewItem(text, board) {
    board.item.push({
        id: cryptp.randomUUID(),
        title: text.value,
    });
}

 
</script>
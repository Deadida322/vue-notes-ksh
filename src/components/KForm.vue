<template>
    <div class="card">
        <div class="card-body">
            <h5 class="card-title">Добавить заметку</h5>
            <div class="card-text">
                <label class="form-label">Название</label>
                <input v-model="note.title" type="text" class="form-control mb-2" />
                <label class="form-label">Описание</label>
                <textarea v-model="note.descrion" type="text" class="form-control" />
            </div>
        </div>
        <div @click="onNoteAdd" class="btn btn-primary m-3 mt-0">Добавить</div>
    </div>
</template>

<script>
import Swal from "sweetalert2"
export default {
    data() {
        return {
            note: {
                title: "",
                description: ""
            }
        }
    },
    methods: {
        onNoteAdd() {
            if (this.note.title) {
                this.$emit("onNoteAdd", { ...this.note })
                this.note = {}
            } else {
                Swal.fire(
                    'Ошибка',
                    'Укажите название заметки',
                    'error'
                )
            }
        }
    }
}
</script>
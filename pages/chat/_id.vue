<template>
    <div class="chat">
        Hola chat
    </div>
</template>

<script>
export default {
    async beforeMount() {
        const token = window.localStorage.getItem('token')
        if (!token) {
            this.$router.push('./login')
        }
        await this.getMessages()       
    },
    methods: {
        async getMessages() {
            try{
                const userOneId = window.localStorage.getItem('userId')
                const userTwoId = this.$route.params.id

                console.log({ userOneId, useTwoId})
            //     const body = JSON.stringify({
            //         userOne,
            //         userTwo,
            //     })
            //    const res = await fetch('http://localhost:4500/message/chat', {
            //        method: 'post',
            //        body
            //    }) 
            //    const data = await res.json()
            //    console.log({ data })
            } catch (err) {
                alert(err)
            }
        }
    }
    
}
</script>
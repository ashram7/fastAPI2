<script>
    import fastapi from "../lib/api"

    export let params = {}
    //Detail 컴포넌트를 호출할때 전달한 파라미터 값을 읽으려면 다음과 같이 params 변수를 선언
    let question_id = params.question_id

    let question = {} 
    function get_question() {
        fastapi("get", "/api/question/detail/" + question_id, {}, (json) => { 
            question = json
        }) 
    }
    get_question()
</script>

<h1>{question.subject}</h1>
<div> 
    {question.content}
</div>
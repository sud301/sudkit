

<script context="module" lang="ts">

export interface Rectangle {
            que: string,
            id: number,
            options: [{
                title: string,
                value: string
            }, {
                title: string,
                value: string
            },
            {
                title: string,
                value: string
            }]
}


export const questions: Array<Rectangle>  = [
        
        {que: "What is sin30",
            id: 1,
            options: [{
                title: "0",
                value: "option1"
            }, {
                title: "1/2",
                value: "option2"
            },
            {
                title: "1",
                value: "option3"
            }]
    
        }, 
        
        
        {que: "Father of Nation",
            id: 2,
            options: [{
                title: "Nehru",
                value: "option1"
            }, {
                title: "Tilak",
                value: "option2"
            },
            {
                title: "Bapu",
                value: "option3"
            }]
        }
    
    ];

</script>
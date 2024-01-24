---
tags:
  - javascript
  - mongo
---

# Working With Databases


```js
// Add Server functions

import db from '$lib/mongo';

  

/** @type {import('./$types').PageServerLoad} */

export async function load() {

let tasks = await db.collection('cards').find({}).toArray();

let cards = JSON.parse(JSON.stringify(tasks));

return {

cards

};

}

  

/**@type {import('./$types').Actions} */

export const actions = {

add: async ({ request }) => {

const data = await request.formData();

const title = data.get('title');

const source = data.get('source');

const link = data.get('link');

const category = data.get('category');

const blurb = data.get('blurb');

const facts = data.get('facts');

const truth = data.get('truth');

const factLink1 = data.get('flink1');

const factLink2 = data.get('flink2');

const TrueVotes = 0;

const FalseVotes = 0;

  

db.collection('cards').insertOne({
title: title,
source: source,
link: link,
category: category,
blurb: blurb,
facts: facts,
truth: truth,
TrueVotes: TrueVotes,
FalaseVotes: FalseVotes,
factLink1: factLink1,
factlink2: factLink2

});

}

};
```


```html
<div class="container">
<div class="add-card">
<form
method="POST"
action="?/add"
use:enhance={({ form }) => {
form.reset();
console.log('card has been added');
}}

>

<input id="title" name="title" type="text" placeholder="Story Title" />
<input id="source" name="source" type="text" placeholder="Source" />
<input id="link" name="link" type="url" placeholder="link" />
<select name="category" id="category">
<option value="politics">Politics</option>
<option value="entertainment">Entertainment</option>
<option value="current-events">Current Events</option>
<option value="spogit push -u origin mainrts">Sports</option>
<option value="education">Education</option>
</select>

<textarea id="blurb" name="blurb" rows="4" cols="100" placeholder="blurb" />
<textarea id="facts" name="facts" rows="4" cols="100" placeholder="Facts" />
<label for="truth-select" />
<select name="truth" id="truth">
<option value="True">True</option>
<option value="False">False</option>
</select>

<input id="flink1" name="flink1" type="url" placeholder="fact link 1" />
<input id="flink2" name="flink2" type="url" placeholder="fact link 2" />
<button class="submit">Submit</button>
</form>
</div>

</div>
```


```javascript
s
const createWorkout = async () => {
                try{
                    const {error} = await supabase.from ("activity").insert([
                        {
                            workoutName: workoutName.value,
                            workoutDay: workoutDay.value,
                            excersises: excersises.value
                        }
                    ])
                    if (error) throw error
                    statusMsg.value = "Day Created"
                    workoutName.value= null
                    workoutDay.value= null
                    excersises.value = null

                }catch(error){
                    errorMsg.value = `Error: ${error.message}`
                    setTimeout(() =>{
                        errorMsg.value = false
                        },5000)
                }
            }
```


```.env

ATLAS_URI2="mongodb+srv://TIS_admin:BMOyOCuxhefcI2oE@tis.pikuv.mongodb.net/?retryWrites=true&w=majority"

ATLAS_URI3="mongodb+srv://TIS_admin:admin@tis.pikuv.mongodb.net/?retryWrites=true&w=majority"

DATABASE_URL="mongodb+srv://TIS_admin:BMOyOCuxhefcI2oE@tis.pikuv.mongodb.net/test"
```

```postgres
CREATE POLICY "Enable insert for all anon users" 
ON public.is_this_correct 
FOR INSERT WITH CHECK 
(auth.role() = 'anon');
```

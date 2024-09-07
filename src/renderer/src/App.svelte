

<div class="svelte" style="font-size:xxx-large; padding-bottom:75px; padding-top:20px">Antichrist Calculator</div>

<input placeholder="Type name here" id="textInput" type="text" bind:value={inputValue} on:input={handleInput} />

<div class="actions" style="padding: 20px;">
  <div style="padding: 10px" class="action">
    <!-- svelte-ignore a11y-click-events-have-key-events a11y-no-static-element-interactions a11y-missing-attribute-->
    <a target="_blank" rel="noreferrer" on:click={() => clean(inputValue)} on:keydown={handleKeydown}>Calculate</a>
  </div>
</div>

<!-- <button on:click={() => clean(inputValue)}
  on:keydown={handleKeydown}>
  Calculate
</button> -->


<!-- <table> -->
  <p style="font-size:x-large; padding-top:25px">Greek: {gname}</p>
  <p style="font-size:x-large; padding: 5px">Hebrew: {hname}</p>
  <p style="font-size:x-large; padding-bottom:5px">Latin: {lname}</p>
<!-- </table> -->
<label for="Extra info" style="align-self:baseline; padding-top:150px;">"Disclaimer: This program doesn't change u's or w's to v's automatically."</label>
<Versions />

<style>
input {
            margin-top: 10px;
            padding: 5px;
            border-radius: 4px;
            border: 1px solid #ccc;
            min-width: 200px;
            min-height: 40px;
            max-height: 100px;
        }
div {
  padding: 10px;
  justify-self: center;
  justify-items: center;
  flex-wrap: wrap;
  align-self: center;
}

/* table{
  justify-items:normal;
} */

</style>

<script>
  import Versions from './components/Versions.svelte'
  // import TextInput from '/components/TextInput.svelte';
  // const ipcHandle = () => window.electron.ipcRenderer.send('ping')
 

  let inputValue = '';
  let cleanedInput = '';
  let inlow = '';
  let hname = '';
  let lname = '';
  let gname = '';

  function handleKeydown(event) {
    if (event.key === 'Enter') {
      clean(inputValue);
    }
  }

  function clean (inp){
    cleanedInput = inp.replace(/[^a-zA-Z]/g, ' ');
	  inlow = cleanedInput.toLowerCase();
      gname = greekCalc(inlow);
	  lname = latinCalc(inlow);
	  hname = hebrewCalc(inlow);
  };
	
	

  // let message = `
	// Name entered: ${inputValue}
	// Greek value: ${gname}	
	// Hebrew value: ${hname}
	// Latin value: ${lname};
  // `

  function latinCalc(ln) {
		//let letterPattern = /[a-zA-Z]/;
		
	  ln = ln.replace(/xviii/g, ",18");
		ln = ln.replace(/xxiii/g, ",23");
				
		ln = ln.replace(/lxxx/g, ",80");
		ln = ln.replace(/dccc/g, ",800");
		ln = ln.replace(/viii/g, ",8");
		ln = ln.replace(/xiii/g, ",13");
		ln = ln.replace(/xxii/g, ",22");
		ln = ln.replace(/xvii/g, ",17");
		ln = ln.replace(/xxiv/g, ",24");


		ln = ln.replace(/iii/g, ",3");
		ln = ln.replace(/ccc/g, ",300");
		ln = ln.replace(/xxx/g, ",30");
		ln = ln.replace(/vii/g, ",7");
		ln = ln.replace(/xxi/g, ",21");
		ln = ln.replace(/lxx/g, ",70");
		ln = ln.replace(/xii/g, ",12");
		ln = ln.replace(/dcc/g, ",700");
		ln = ln.replace(/cii/g, ",102");
		ln = ln.replace(/xix/g, ",19");
		ln = ln.replace(/xiv/g, ",14");
		ln = ln.replace(/xvi/g, ",16");

		ln = ln.replace(/ii/g, ",2");
		ln = ln.replace(/xx/g, ",20");
		ln = ln.replace(/cc/g, ",200");
		ln = ln.replace(/xv/g, ",15");
		ln = ln.replace(/xl/g, ",40");
		ln = ln.replace(/xc/g, ",90");
		ln = ln.replace(/lx/g, ",60");
		ln = ln.replace(/iv/g, ",4");
		ln = ln.replace(/vi/g, ",6");
		ln = ln.replace(/ix/g, ",9");
		ln = ln.replace(/xi/g, ",11");
		ln = ln.replace(/ci/g, ",101");
		ln = ln.replace(/cd/g, ",400");
		ln = ln.replace(/dc/g, ",600");
		ln = ln.replace(/cm/g, ",900");

	 	ln = ln.replace(/i/g, ",1");
		ln = ln.replace(/v/g, ",5");
		ln = ln.replace(/x/g, ",10");
		ln = ln.replace(/l/g, ",50");
		ln = ln.replace(/c/g, ",100");
		ln = ln.replace(/d/g, ",500");
		ln = ln.replace(/m/g, ",1000");

		// Replace the characters with no value
		ln = ln.replace(/a/g, " ")
		ln = ln.replace(/b/g, " ")
		ln = ln.replace(/e/g, " ")
		ln = ln.replace(/f/g, " ")
		ln = ln.replace(/g/g, " ")
		ln = ln.replace(/h/g, " ")
		ln = ln.replace(/j/g, " ")
		ln = ln.replace(/k/g, " ")

		ln = ln.replace(/n/g, " ")
		ln = ln.replace(/o/g, " ")
		ln = ln.replace(/p/g, " ")
		ln = ln.replace(/q/g, " ")
		ln = ln.replace(/r/g, " ")
		ln = ln.replace(/s/g, " ")
		ln = ln.replace(/t/g, " ")
		ln = ln.replace(/u/g, " ")
		ln = ln.replace(/w/g, " ")
		ln = ln.replace(/y/g, " ")
		ln = ln.replace(/z/g, " ")
		
	 	ln = ln.split(',');
	 	let w = 0;
			
		ln.forEach(element => {
			w = w + Number(element);
		});

    let amnt = 0;
		amnt = w;
    if (w === 666){
      amnt = w + '  The Beast?'
    }
		return amnt;
	 }

 function greekCalc(gn) {
		//let letterPattern = /[a-zA-Z]/;
				
		gn = gn.replace(/sampi/g, ",900");
		gn = gn.replace(/th/g, ",9");
		gn = gn.replace(/rh/g, ",100");
		gn = gn.replace(/ph/g, ",500");
		gn = gn.replace(/kh/g, ",600");
		gn = gn.replace(/ps/g, ",700");
		gn = gn.replace(/st/g, ",6");
		gn = gn.replace(/a/g, ",1")
		gn = gn.replace(/b/g, ",2")
		gn = gn.replace(/g/g, ",3")
		gn = gn.replace(/d/g, ",4")
		gn = gn.replace(/e/g, ",5")
		gn = gn.replace(/w/g, ",6")
		gn = gn.replace(/z/g, ",7")
		gn = gn.replace(/ē/g, ",8")
		gn = gn.replace(/i/g, ",10")
		gn = gn.replace(/k/g, ",20"),
		gn = gn.replace(/l/g, ",30"),
		gn = gn.replace(/m/g, ",40"),
		gn = gn.replace(/n/g, ",50"),
		gn = gn.replace(/x/g, ",60"),
		gn = gn.replace(/o/g, ",70"),
		gn = gn.replace(/p/g, ",80"),
		gn = gn.replace(/q/g, ",90")
		gn = gn.replace(/r/g, ",100")
		gn = gn.replace(/s/g, ",200")
		gn = gn.replace(/t/g, ",300")
		gn = gn.replace(/u/g, ",400")
		gn = gn.replace(/ō/g, ",800")

		// Replace the characters with no value
		gn = gn.replace(/f/g, " ")
		gn = gn.replace(/h/g, " ")
		gn = gn.replace(/j/g, " ")
		gn = gn.replace(/c/g, " ")
		gn = gn.replace(/v/g, " ")
		gn = gn.replace(/y/g, " ")
		
	 	gn = gn.split(',');
	 	let y = 0;
			
		gn.forEach(element => {
			y = y + Number(element);
		});

    let amt = 0;
		amt = y;
    if (y === 666){
      amt = y + '  The Beast?'
    }
		return amt;
	 }


 function hebrewCalc(hn) {
				
		hn = hn.replace(/sh/g, ",300");
		hn = hn.replace(/ch/g, ",8");
		hn = hn.replace(/th/g, ",400");
		hn = hn.replace(/ts/g, ",90");
		hn = hn.replace(/a/g, ",1")
		hn = hn.replace(/b/g, ",2")
		hn = hn.replace(/g/g, ",3")
		hn = hn.replace(/d/g, ",4")
		hn = hn.replace(/h/g, ",5")
		hn = hn.replace(/v/g, ",6") //could be "w" in older text 
		hn = hn.replace(/z/g, ",7")
		hn = hn.replace(/t/g, ",9")
		hn = hn.replace(/y/g, ",10")
		hn = hn.replace(/k/g, ",20"),
		hn = hn.replace(/l/g, ",30"),
		hn = hn.replace(/m/g, ",40"),
		hn = hn.replace(/n/g, ",50"),
		hn = hn.replace(/s/g, ",60"),
		// hn = hn.replace(/ʿ/g, ",70"), also removes nonletter symbols
		hn = hn.replace(/p/g, ",80"),
		hn = hn.replace(/f/g, ",80"),
		hn = hn.replace(/q/g, ",100")
		hn = hn.replace(/r/g, ",200")

		// Replace the characters with no value
		hn = hn.replace(/e/g, " ")
		hn = hn.replace(/o/g, " ")
		hn = hn.replace(/w/g, " ")
		hn = hn.replace(/c/g, " ")
		hn = hn.replace(/i/g, " ")
		hn = hn.replace(/j/g, " ")
		hn = hn.replace(/u/g, " ")
		hn = hn.replace(/x/g, " ")
		
	 	hn = hn.split(',');
	 	let x = 0;
			
		hn.forEach(element => {
			x = x + Number(element);
		});
    let amount = 0;
		amount = x;
    if (x === 666){
      amount = x + '  The Beast?'
    }
		return amount;
	 }
   

      function handleInput(event) {
          inputValue = event.target.value;
          console.log('Input Value:', inputValue);
		  
      }

</script>

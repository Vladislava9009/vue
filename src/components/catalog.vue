<template>
    <div class="wrapper">
            <h1>Items catalog</h1>
            <div class="search"> 
                    <form action="option1.php">
                    <p><select name="hero">
                    <option selected value="t1">All</option>
                    <option value="t2">Зимние шины</option>
                    <option value="t3">Летние шины</option>
                    <option value="t4">Всесезонные шины</option>
                    </select>
                    <input type="submit" value="Отправить"></p>
                    </form>
                    <input type="search" placeholder="Search">
            </div>
            <table class="table table-striped" id="table">
  
</table>
    </div>
</template>
<script>
 export default{
     data(){
         return{
             
         }
     }
 }
function ajax(url){
	return fetch(url).then(response=> response.json());
}
ajax('./test/items.json')
.then(response=>{
  let item = response.items;
  
       var body = document.getElementsByTagName("body")[0];
      
        var tbl     = document.createElement("table");
        var tblBody = document.createElement("tbody");
       tbl.classList.add('table');
       tbl.classList.add('table-striped');
       
        
           item.forEach(element => { 
            var row = document.createElement("tr");
         
                    for (var key in element) {
                      console.log(element[key])
	                var cell = document.createElement("td");    
                  var cellText = document.createTextNode(element[key]); 
        if( element[key] == "link") {
		        	let img = document.createElement('img');
              img.src="https://shyp-shyna.com.ua/upload/images/tyres/detail/185_65r15_m_s_88h_viamaggiore_z_plus_premiorri_shina0.jpg";
              row.appendChild(img)
	    	} else{
          cell.appendChild(cellText); 
      
                      row.appendChild(cell);
       }
                   
                  }
             
                
            

            tblBody.appendChild(row);
                
        tbl.appendChild(tblBody);
        
        body.appendChild(tbl);
        
        tbl.setAttribute("border", "2");
    
   })
 
})
.catch(error=>{
	console.log(error);
});

</script>

<style >
.search{
    display:flex;
    justify-content:space-between;
}
select,
input{
width: 212px;
height: 49px;
background: #F4F4F4;
border: 1px solid #C8CBCC;
box-sizing: border-box;
border-radius: 4px;
}
,tr{
  max-height:50px;
}
    
</style>

#always use normal function instead of es6 function

Array.prototype.test=()=>{
    console.log(this)
}

Array.prototype.Mytest=function(){
    console.log(this)
}


let arr=[4,12,13,8,20]

arr.test()

arr.Mytest()

# π» MatrixCalculator
https://user-images.githubusercontent.com/114633506/212219799-e71b97a6-ede3-4d1b-89d4-5ea39628291a.mp4

<br>

## π© About
- **μμκΈ°κ°** : 2022.11.28 - 2022.11.29  
- **μ°Έμ¬λ** : 100%  
- **κΈ°μ ** : λ°λλΌ μλ°μ€ν¬λ¦½νΈ  

<br>

## π· κΈ°λ₯
- μ΅λ 6ν 6μ΄μ νμ΄λΈμ λ§λ€ μ μμ΅λλ€.  
- μ«μλ₯Ό μ§μ  μλ ₯νκ±°λ λλ€ λλ all one λ²νΌμ ν΄λ¦­νμ¬ μ«μλ₯Ό μμ±ν  μ μμ΅λλ€.  
- μ’μ° νμ΄λΈμ νκ³Ό μ΄μ΄ μΌμΉνμ§ μκ±°λ κ°μ΄ μ ν¨νμ§ μμ κ²½μ° κ²½κ³ μ°½μ λμλλ€.  


### μ£Όμμ½λ β­ 
<details>
<summary>νλ ¬λ°μ€ λ§λ€κΈ°</summary>  
  
```c
let aCol = 0;
let aRow = 0;

aMatrix.addEventListener("click", () => {
    aRow = aBoxRow.value;
    aCol = aBoxCol.value;

    if(aRow === "") {
        alert("Aμ νμ μλ ₯νμΈμ.");
        return false;
    }

    if(aCol === "") {
        alert("Aμ μ΄μ μλ ₯νμΈμ.");
        return false;
    }

    let aTableStr = "<table>";
    for(let i = 0; i < aCol; i++) {
        aTableStr += "<tr>";
        for(let j = 0; j < aRow; j++) {
            aTableStr += `<td><input class='aInputClass' id='aNumber${i}${j}' type ='text' maxlength='4' min='0' max='100' step='1' oninput= \"this.value = this.value.replace(/[^0-9.]/g, '');\"></td>`;
        }
        aTableStr += "</tr>";
    }
    aTableStr += "</table>";
    outputA.innerHTML = aTableStr;
}, false);

```

</details>  
  
<details>
<summary>λνκΈ°</summary>  
  
```c
plusBtn.addEventListener("click", () => {
if(aCol == "" || bCol == "" || aRow == "" || bRow == "") {
    alert("Aμ Bμ νκ³Ό μ΄μ μμ±νμΈμ.");
    return false;
}

if(aCol !== bCol || aRow !== bRow) {
    alert("Aμ Bμ νκ³Ό μ΄μ κ°κ² μλ ₯νμΈμ.");
    return false;
}

let num = "";
let answer = "";
let abTableStr = "<table>";
for(let i = 0; i < aCol; i++) {
    abTableStr += "<tr>";
    for(let j = 0; j < bRow; j++) {
        if(document.getElementById(`bNumber${i}${j}`).value == "" || document.getElementById(`aNumber${i}${j}`).value == "") {
            alert("λΉ κ°μ μλ ₯ν΄μ£ΌμΈμ.");
            return false;
        } else {
            abTableStr += "<td><span class='abInputClass'>";
            abTableStr += (Number(document.getElementById(`aNumber${i}${j}`).value)) + (Number(document.getElementById(`bNumber${i}${j}`).value));
            abTableStr += "</td>";
        }
    }
    abTableStr += "<tr>";
}
abTableStr += "</table>";
num = abTableStr;
answer = num.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");

outputAB.innerHTML = answer;
outputAB.value = "";

window.scrollTo({top:location, behavior: 'smooth'});
}, false);

```

</details>  
  
<details>
<summary>λλ€ λ²νΌ</summary>  
  
```c
randomBtn.addEventListener("click", () => {
if(aCol == "" || bCol == "" || aRow == "" || bRow == "") {
    alert("Aμ Bμ νκ³Ό μ΄μ μμ±νμΈμ.");
    return false;
}

// A νλ ¬ λλ€
let abTableStr = "<table>";
for(let i = 0; i < aCol; i++) {
    abTableStr += "<tr>";
    for(let j = 0; j < aRow; j++) {
        abTableStr += "<td><span class='abInputClass'>";
        abTableStr += Number(document.getElementById(`aNumber${i}${j}`).value = Math.floor(Math.random() * 50));
        abTableStr += "</span></td>";
    }
    abTableStr += "</tr>";
}
abTableStr += "</table>";

```

</details>

<br>

## π¬ λλμ 
λ°λλΌ μλ°μ€ν¬λ¦½νΈλ‘ κ΅¬νν μ²« μλ°μ€ν¬λ¦½νΈ ν¬νΈν΄λ¦¬μ€λ€. 
νλ ¬κ³μ°κΈ° μ½λλ κ΅¬κΈμ κ²μνλ©΄ κ΅μ₯ν λ§μλ°, λλΆλΆ μ μ΄μΏΌλ¦¬λ‘ λμ΄ μλ€. 
μ μ΄μΏΌλ¦¬ μ½λλ₯Ό μ°Έκ³ νλ©΄μ μ΄λ»κ² νλ©΄ λ°λλΌ JSλ‘ κ΅¬νν  μ μλμ§ κ³ λ―Όνλ©° μ½λλ₯Ό μμ±νλ€.

<br>

## π¦ κ°μ ν  μ 
κ³μ° κΈ°λ₯μ΄ λ§μ, λΊμ, κ³±μ μ΄λ κ² 3κ°μ§ λ°μ μλ λ¨μν ννλΌ μμ½λ€. μ€μ  νλ ¬κ³μ° μ¬μ΄νΈμ λ€μ΄κ°λ©΄ λ€μν κ³μ°μ΄ κ°λ₯νλ°, λλ κΈ°λ₯μ λͺ κ°μ§ λ μΆκ°νκ³  μΆλ€.
(*κ·Έμ μ μν κ³΅λΆκ° λ¨Όμ μΌ κ² κ°μ...?*)





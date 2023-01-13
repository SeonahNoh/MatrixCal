# 💻 MatrixCalculator
<img src="https://user-images.githubusercontent.com/114633506/212217090-6210f0f3-f182-40e9-8760-37865d77abae.png" width="800" height="auto">

<br>

## 🍩 About
- **작업기간** : 2022.11.28 - 2022.11.29  
- **참여도** : 100%  
- **기술** : 바닐라 자바스크립트  

<br>

## 🌷 기능
- 최대 6행 6열의 테이블을 만들 수 있습니다.  
- 숫자를 직접 입력하거나 랜덤 또는 all one 버튼을 클릭하여 숫자를 생성할 수 있습니다.  
- 좌우 테이블의 행과 열이 일치하지 않거나 값이 유효하지 않은 경우 경고창을 띄웁니다.  


### 주요코드 ⭐ 
<details>
<summary>행렬박스 만들기</summary>  
  
```c
let aCol = 0;
let aRow = 0;

aMatrix.addEventListener("click", () => {
    aRow = aBoxRow.value;
    aCol = aBoxCol.value;

    if(aRow === "") {
        alert("A의 행을 입력하세요.");
        return false;
    }

    if(aCol === "") {
        alert("A의 열을 입력하세요.");
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
<summary>더하기</summary>  
  
```c
plusBtn.addEventListener("click", () => {
if(aCol == "" || bCol == "" || aRow == "" || bRow == "") {
    alert("A와 B의 행과 열을 생성하세요.");
    return false;
}

if(aCol !== bCol || aRow !== bRow) {
    alert("A와 B의 행과 열을 같게 입력하세요.");
    return false;
}

let num = "";
let answer = "";
let abTableStr = "<table>";
for(let i = 0; i < aCol; i++) {
    abTableStr += "<tr>";
    for(let j = 0; j < bRow; j++) {
        if(document.getElementById(`bNumber${i}${j}`).value == "" || document.getElementById(`aNumber${i}${j}`).value == "") {
            alert("빈 값을 입력해주세요.");
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
<summary>랜덤 버튼</summary>  
  
```c
randomBtn.addEventListener("click", () => {
if(aCol == "" || bCol == "" || aRow == "" || bRow == "") {
    alert("A와 B의 행과 열을 생성하세요.");
    return false;
}

// A 행렬 랜덤
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

// B 행렬 랜덤
let abTableStr2 = "<table>";
for(let i = 0; i < bCol; i++) {
    abTableStr2 += "<tr>";
    for(let j = 0; j < bRow; j++) {
        abTableStr2 += "<td><span class='abInputClass'>";
        abTableStr2 += Number(document.getElementById(`bNumber${i}${j}`).value = Math.floor(Math.random() * 50));
        abTableStr2 += "</span></td>";
    }
    abTableStr2 += "</tr>";
}
abTableStr2 += "</table>";
}, false);

```

</details>

<br>

## 💬 느낀점
바닐라 자바스크립트로 구현한 첫 자바스크립트 포트폴리오다. 
행렬계산기 코드는 구글에 검색하면 굉장히 많은데, 대부분 제이쿼리로 되어 있다. 
제이쿼리 코드를 보면서 어떻게 하면 바닐라 JS로 구현할 수 있는지 고민하며 코드를 작성했다.

<br>

## 💦 개선할 점
- 계산 기능이 덧셈, 뺄셈, 곱셈 이렇게 3가지 밖에 없는 단순한 형태라 아쉽다. 실제 행렬계산 사이트에 들어가면 다양한 계산이 가능한데, 나도 기능을 몇 가지 더 추가하고 싶다.
(*그전에 수학 공부가 먼저일 것 같은...?*)





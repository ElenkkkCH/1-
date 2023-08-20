const startHalfStr = (str) => str.slice(0, str.length / 2);

const endHalfStr = (str) => {
  if (str.length % 2 == 0) return str.slice(str.length / 2, str.length);
  return str.slice(str.length / 2 + 1, str.length);
};

const reversStr = (str) => str.split("").reverse().join("");

const onlyAlhabet = (str) => {
  let alhabetEn = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
  let alhabetRu =
    "абвгдеёжзийклмнопрстуфхцчшщъыьэюяАБВГДЕЁЖЗИЙКЛМНОПРСТУФХЦЧШЩЪЫЬЭЮЯ";

  let newStr = "";

  for (let i = 0; i < str.length; i++) {
    let letter = str[i];
    if (alhabetEn.includes(letter) || alhabetRu.includes(letter)) {
      newStr += letter;
    }
  }

  return newStr;
};

function palindrome(str) {
  let letters = onlyAlhabet(str);
  return (
    startHalfStr(letters).toUpperCase() ===
    reversStr(endHalfStr(letters)).toUpperCase()
  );

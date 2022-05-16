<img align="center" src="https://myozzy.me/github/adminc.jpg" alt="Uzgur" min-height="200" width="1200" />
<br>

[![Typing SVG](https://readme-typing-svg.herokuapp.com?size=40&color=ED15F7&center=true&width=1200&height=150&lines=RageMP+%D0%B0%D0%B4%D0%BC%D0%B8%D0%BD+%D0%BA%D0%BE%D0%BC%D0%B0%D0%BD%D0%B4%D1%8B;(%D0%A1%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D0%BD%D1%8B%D0%B5+%D0%BA%D0%BE%D0%BC%D0%B0%D0%BD%D0%B4%D1%8B);%D0%B1%D0%B5%D0%B7+%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B8+%D1%83%D1%80%D0%BE%D0%B2%D0%BD%D1%8F+%D0%B0%D0%B4%D0%BC%D0%B8%D0%BD%D0%B0)](https://git.io/typing-svg)
<br><br>

<h3 align="left">⚙️Краткая инструкция:</h3>
<p align="left">
<b>
/hp id 100 (Восстановление жизни)<br>
/arm id 100 (Восстановление брони)<br>
/veh vehname color1 color2 (Спавн машины)<br>
/fixcar id (Восстановление транспорта)<br>
/pos (Координаты игрока)<br>
/pos (Координаты игрока)<br>
/tpc x, y, z (Телепорт по координатам)<br>
/setw weathername (Смена погоды)<br>
/gethere id (Телепортиртация игрока)<br>
/goto id (Телепортироваться к игроку)<br>
/setdim id dim (/Смена дименшина)<br>
/gun id weapon ammo (Спавним оружие в руках)<br>
/dim (Проверка дименшина)<br>
/banhd id reason (Бан по железу)<br>
/setcloth component drawable (Одежда)<br>
/delveh (Удаление машин)<br>
/clshape name r g b a colshape_radius marker_id type price (Пытаемся заспавнить колшейпы)<br>
/anim animDic animName duration flag (Прокрут анимации)<br>
/scanim scenario (Прокрут сценарий)<br></b>
</p><br>
Файл с командами находится по пути /packages/server_name/command/admin.js <br>

<h3 align="left">📝Пример для проверки админ уровня:</h3><br>

```
 mp.events.add("playerChat", (player, input) => {
  if (input.charAt(0) == "!") {
    input = input.substr(1);
    for (com in commandsList) {
      let args = input.split(" ");
      if (args[0] == com) {
        if (player.getAdminlvl() < commandsList[com].adminLvl)
          return player.outputChatBox(
            `Для использование данной команды, вы должны быть администратором ${commandsList[com].adminLvl} уровня!`
          );
        args = args.slice(1);
        if ((commandsList[com].args && args.length == 0) || args[0] == "?")
          return player.outputChatBox(commandsList[com].desc);
        commandsList[com].func(player, args);
      }
    }
  }
});
```



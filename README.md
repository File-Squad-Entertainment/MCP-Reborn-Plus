## MCP-Reborn [![Build Status](https://github.com/Hexeption/MCP-Reborn/workflows/Java%20CI/badge.svg)](https://github.com/Hexeption/MCP-Reborn/actions?workflow=Java+CI)
RU/RUS
#### MCP-Reborn — это MCP (Mod Coder Pack) для Minecraft для создания модифицированных клиентов для Minecraft и исследования его кода. Он основан на MCPConfig и ForgeGradle от MinecraftForge Team.

### :warning: ПРЕДУПРЕЖДЕНИЕ :warning:: Вы **МОЖЕТЕ** публиковать какой-либо код, сгенерированный этим ремейком.

### Поддерживаемые версии:
1.13->1.20.2

### Важно
1.17< Требуется JDK 16

1.18> Требуется JDK 17

### Как использовать

1. Импортируйте build.gradle в Intellij.

2. Запустите задачу Gradle "setup" в папке mcp в IntelliJ — вам может потребоваться выбрать View > Tool Windows > Gradle, чтобы получить эту опцию.

<img width="284" alt="373de4ebc77d5079584370dd7fbe8745" src="https://user-images.githubusercontent.com/4052647/46925924-71b7b680-d026-11e8-9c29-e3ed2e43f810.png">

Это сгенерирует декомпилированный исходный код, который теперь можно найти в папке "src" в проекте.

3. Измените исходный код по своему усмотрению.

4. Чтобы протестировать измененный код, вернитесь к списку задач Gradle (где вы запускали настройку) и запустите задачу "runclient".
Это скомпилирует вашу новую, измененную игру и запустит ее, чтобы вы могли протестировать ее.<br>**Примечание: вы также можете запустить автоматически сгенерированную конфигурацию запуска «Minecraft»**

5. Как только вы достигли окончательного результата, которым вы довольны, есть небольшой процесс, чтобы превратить его в файл JAR, который
можно запустить из лаунчера игры. Перейдите в папку «build» в задачах Gradle и запустите задачу «build». Это
сгенерирует новый исполняемый файл JAR в каталоге «build/libs/».

<img width="266" alt="a647ab0eb336062ffd80c8e053e10266" src="https://user-images.githubusercontent.com/4052647/46925963-a297eb80-d026-11e8-8b02-cb621b559511.png">

6. Сгенерировав этот JAR, откройте папку версий Minecraft. В Linux это по умолчанию `~/.minecraft/versions`. В Windows это `AppData/Roaming/.minecraft/versions`. Найдите вариант, на котором основана ваша модифицированная версия (то есть, если
вы модифицировали 1.16.4, найдите папку 1.16.4). Дублируйте эту папку и переименуйте ее. Я модифицировал villagers, поэтому
я назвал его «1.16.4_villager_mod».

7. Перейдите в эту папку и удалите оригинальный файл JAR Minecraft. Затем переименуйте файл JSON, чтобы он был идентичен
имени папки. Для меня это было «1.16.4_villager_mod.json».

8. Используя текстовый редактор, найдите первый экземпляр «downloads»: это сообщает Minecraft, где получить файл JAR игры.
Если вы оставите это, Minecraft автоматически загрузит ванильный JAR. Но мы хотим запустить ваш новый модифицированный JAR.
Итак, удалите все из этих "загрузок": через заголовки client, server и server_mappings, которые в конечном итоге заканчиваются
на `/server.txt"}},`. После того, как вы удалите это, этот раздел должен содержать `"assets": "1.16", "complianceLevel": 1, "id": "1.16.4"`.
Последнее, что нам нужно сделать в этом файле JSON, — это изменить это поле ID, чтобы оно соответствовало имени папки и
файла JSON. Так что в этом случае нам нужно `"id":"1.16.4_villager_mod"`.

9. Теперь возьмите ваш новый файл JAR из каталога build/libs/ и скопируйте его в эту же папку версии, и, в последний раз, переименуйте его в новое имя, которое мы использовали — 1.16.4_villager_mod.jar.

10. Используйте менеджер архивов (Ubuntu поставляется со встроенным менеджером; пользователи Windows могут загрузить 7-Zip), откройте файл JAR базовой версии (в данном случае 1.16.4.jar, который вы найдете в его папке) и ваш файл JAR. Вам нужно будет скопировать 4
файла/папки из базового JAR в ваш новый.

1. Папка "assets"
2. Папка "data"
3. Файл "pack.png"
4. Файл "pack.mcmeta"

11. Наконец, все еще в этом менеджере архивов, удалите папку META-INF из вашего нового JAR.

12. Теперь все ваши файлы должны быть настроены. В лаунчере Minecraft (закройте и снова откройте его, если он уже открыт) перейдите в раздел
"Installations" в левом верхнем углу, а затем создайте новую установку. Назовите ее как хотите. Для версии выберите
созданную вами версию (1.16.4_villager_mod.jar). Создайте его, затем вернитесь на главный экран лаунчера, нажав «Воспроизвести» в левом верхнем углу. В левом нижнем углу выберите новую пользовательскую версию и нажмите большую зеленую кнопку «Воспроизвести».

### Как добавить Optifine

[![](https://img.youtube.com/vi/ocz1tPI_YSE/0.jpg)](https://www.youtube.com/watch?v=ocz1tPI_YSE «Как добавить Optifine в MCP Reborn»)

### Создатели:

* Hexeption
* kingdevnl

### Ремейкеры:

* Savely22827
#### Особая благодарность: команде **MinecraftForge**, Hexeption и kingdevnl, которые сделали этот ремейк возможным. ❤

EN/ENG:
#### MCP-Reborn is an MCP (Mod Coder Pack) for minecraft for making modded clients for minecraft and researching its code. It is based on MCPConfig and ForgeGradle by MinecraftForge Team.

### :warning: WARNING :warning:: You **MAY** post any code generated by this remake.

### Supported versions:
1.13->1.20.2

### Important
1.17< Needs JDK 16

1.18> Needs JDK 17

### How to use

1. Import the build.gradle in Intellij.

2. Run the Gradle "setup" task in the mcp folder in IntelliJ - you may need to select View > Tool Windows > Gradle to get this option.

    <img width="284" alt="373de4ebc77d5079584370dd7fbe8745" src="https://user-images.githubusercontent.com/4052647/46925924-71b7b680-d026-11e8-9c29-e3ed2e43f810.png">

    This will generate the decompiled source code, which you can now find in the "src" folder in the project.

3. Modify the source code as you please.

4. To test your modified code, go back to the Gradle tasks list (where you ran setup), and run the "runclient" task.
  This will compile your new, modified game and run it, to allow you to test.<br>**Note: You can also run the autogenerated run configuration 'Minecraft'**

5. Once you have reached a final result you are happy with, there is a bit of a process to turn it into a JAR file that
  can actually run from the game launcher. Go to the "build" folder in the Gradle tasks, and run the "build" task. This
  will generate the new executable JAR file in the "build/libs/" directory.
  
    <img width="266" alt="a647ab0eb336062ffd80c8e053e10266" src="https://user-images.githubusercontent.com/4052647/46925963-a297eb80-d026-11e8-8b02-cb621b559511.png">

6. With that JAR generated, open your Minecraft versions folder. On Linux, this defaults to `~/.minecraft/versions`. On
  Windows, it's in `AppData/Roaming/.minecraft/versions`. Find the variant your modded version is based on (that is, if
  you modded 1.16.4, find the 1.16.4 folder). Duplicate that folder, and rename it. For me, I was modifying villagers so
  I called it "1.16.4_villager_mod".

7. Go into that folder and delete the original Minecraft JAR file. Then, rename the JSON file to be identical to the
  folder name. For me, that made it "1.16.4_villager_mod.json".

8. Using a text editor, find the first instance of "downloads": This tells Minecraft where to obtain the game JAR file.
  If you leave this in, Minecraft will automatically download the vanilla JAR. But we want to run your new modded JAR.
  So delete everything from that "downloads": through the client, server, and server_mappings headers, which finally end
  in `/server.txt"}},`. Once you remove that, this section should hold `"assets": "1.16", "complianceLevel": 1, "id": "1.16.4"`.
  The last thing we need to do in this JSON file is to change that ID field to match the name of the folder and the
  JSON file. So in this case, we want `"id":"1.16.4_villager_mod"`.

9. Now, take your new JAR file from the build/libs/ directory, and copy it into this same version folder, and, for the
  final time, rename it to the new name we've been using - 1.16.4_villager_mod.jar.

10. Using an archive manager (Ubuntu comes with one built in; Windows users can download 7-Zip), open the base version's
  JAR file (in this case, 1.16.4.jar, which you'll find in its folder), and your JAR file. You'll need to copy 4
  files/folders from the base JAR into your new one.

    1. The folder "assets"
    2. The folder "data"
    3. The file "pack.png"
    4. The file "pack.mcmeta"

11. Finally, still in that archive manager, delete the META-INF folder from your new JAR.

12. Your files should all be configured now. In the Minecraft launcher (close and reopen it if it's already open), go to
  "Installations" in the upper left, and then create a new installation. Name it whatever you want. For the version, select
  the version you made (1.16.4_villager_mod.jar). Create it, then go back to the launcher home screen by clicking "Play" in
  the upper left. In the lower left, select your new custom version, and hit the big green "Play" button.

### How to add Optifine

[![](https://img.youtube.com/vi/ocz1tPI_YSE/0.jpg)](https://www.youtube.com/watch?v=ocz1tPI_YSE "How to add Optifine to MCP Reborn")

### Creators:

* Hexeption
* kingdevnl

### Remakers:

* Savely22827
#### Special thanks to: The **MinecraftForge** team, Hexeption and kingdevnl who made this remake possible. ❤

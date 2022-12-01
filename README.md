# LR5

Кириченко Антон

ЭВТ-70

Игровой Движок: Unity.

Лабораторная работа №5

Тема: разработка игры 2D Endless Runner 

Цель: разработать игру 2D Endless Runner

1)Создаем Проект и импортируем туда папку с  Assets и Sprites
 ![image](https://user-images.githubusercontent.com/119482774/205072967-f6b9f031-5674-4f85-842b-e19860853dea.png)

Рисунок 4.1 Импортированная папка Assets
 ![image](https://user-images.githubusercontent.com/119482774/205073006-da86aa6e-b1cb-436d-8af6-1c5be0ec42b3.png)

Рисунок 4.2 Папка Assets с данными
2) Добавляем Два Объекта Player  и Player Sprites. Настраиваем их
 ![image](https://user-images.githubusercontent.com/119482774/205073045-c44c9068-8d55-4a65-afe6-b86efc16c095.png)

Рисунок 4.3 Объекты Player  и Player Sprites
 ![image](https://user-images.githubusercontent.com/119482774/205073059-2d4eec5f-18dc-4ee1-96ab-9465437fde62.png)

Рисунок 4.4 Настройка Player Sprites
 
 ![image](https://user-images.githubusercontent.com/119482774/205073133-ebb54d47-d69a-4c08-9507-17d4fbae3238.png)

Рисунок 4.5 Настройка Player
3) Создаём Папку Scripts и Добавляем код  для взаимодействием с Player – объектом, а также его движениями 
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Player : MonoBehaviour
{
    public float playerSpeed;
    private Rigidbody2D rb;
    private Vector2 playerDirection;
    void Start()
    {
        rb = GetComponent<Rigidbody2D>();
    }

    void Update()
    {
        float directionY = Input.GetAxisRaw("Vertical");
        playerDirection = new Vector2(0, directionY).normalized;
    }
    private void FixedUpdate()
    {
        rb.velocity = new Vector2(0, playerDirection.y * playerSpeed);
    }
}
 

4) Добавляем код  для Движений Камеры
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class CameraMovement : MonoBehaviour
{
    
    public float cameraSpeed;

 
    void Update()
    {
        transform.position += new Vector3(cameraSpeed * Time.deltaTime, 0, 0);
    }
}
```
ВЫВОД: Входе проделанной работы была разработана игра  2D Endless Runner

[ЛР5. Создание игры Endless Runner.zip](https://github.com/Userfall3000/LR5/files/10133022/5.Endless.Runner.zip)

# Виртуальная и дополненная реальность
Отчет по лабораторной работе #1 выполнил(а):
- Сиверухин Никита Андреевич
- РИ-300021
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | # | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 2.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 3.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Выводы.
- ✨Magic ✨

## Цель работы
Ознакомиться с основными функциями Unity и взаимодействием с объектами внутри редактора.

## Задание 1
### В разделе «ход работы» пошагово выполнить каждый пункт с описанием и примера реализации задач по теме видео самостоятельной работы.
Ход работы:
1) Создать новый проект из шаблона 3D – Core;
2) Проверить, что настроена интеграция редактора Unity и Visual Studio Code (пункты 8-10 введения);
3) Создать объект Plane;
4) Создать объект Cube;
5) Создать объект Sphere;
6) Установить компонент Sphere Collider для объекта Sphere;
7) Настроить Sphere Collider в роли триггера;
8) Объект куб перекрасить в красный цвет;
9) Добавить кубу симуляцию физики, при это куб не должен проваливаться под Plane;
10) Написать скрипт, который будет выводить в консоль сообщение о том, что объект Sphere столкнулся с объектом Cube;
11) При столкновении Cube должен менять свой цвет на зелёный, а при завершении столкновения обратно на красный.

Cкрипт, который будет выводить в консоль сообщение о том, что объект Sphere столкнулся с объектом Cube; При столкновении Cube меняет свой цвет на зелёный, а при завершении столкновения обратно на красный
```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class CheckCollider : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        
    }

    private void OnTriggerEnter(Collider other) {
        Debug.Log("Произошло столкновение с " + other.gameObject.name);
        other.GetComponent<Renderer>().material.SetColor("_Color", Color.green);
    }

    private void OnTriggerExit(Collider other) {
       Debug.Log("Завершино столкновение с " + other.gameObject.name);
       other.GetComponent<Renderer>().material.SetColor("_Color", Color.red);
    }
}
```

## Задание 2
### Продемонстрируйте на сцене в Unity следующее:
- Что произойдёт с координатами объекта, если он перестанет быть дочерним?
- Создайте три различных примера работы компонента RigidBody?
Ответ:
1)Из родительской точки 0 берется берутся координаты дочернего объекта. Если перетащить объект и сделать его родительским, то его координаты сменят числовое значение относительно всей сцены, но объект положения не поменяет.

2)Параметром Use Gravity отвечает за гравитацию объекта. IsKinematic при включении отвечает за то, что на объект больше не действует никакая физиак, так например, если его толкнули, или заставили вращаться, то действие сли просто прекратится Так, поскольку надо было выполнить три пункта, то я ещё настраивал вес объекта. Как оказалось, этот параметр влияет на импульс объекта при соприкосновенни. Вес объекта, этот параметр влияет на импульс объекта при соприкосновенни. Так, если вес объекта 0, то после удара о другой объект, на этот друго объект не будет действовать никакая сила

## Выводы
В этой лабораторной работе, я ознакомиться с основными функциями Unity и взаимодействием с объектами внутри редактора.

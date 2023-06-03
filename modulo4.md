using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using System;
public class VRCamera : MonoBehaviour
{ // marca para realizar un seguimiento de si estamos arrastrando o no
    public bool isDragging = false;

    // punto de partida de un movimiento de cámara
    float startMouseX;
    float startMouseY;

    // componente de la cámara
    public Camera cam;
    // Se llama al inicio antes de la primera actualización del cuadro
    void Start()
    {
        // Obtenga nuestro componente de cámara

        cam = this.gameObject.GetComponent<Camera>();
    }

    // La actualización se llama una vez por cuadro
    void Update()
    {

        // si pulsamos el botón izquierdo y no hemos empezado a arrastra
        if (Input.GetMouseButtonDown(0) && !isDragging)
        {
            // establecer la bandera en verdadero
            isDragging = true;

            // guardar la posición inicial del mouse
            startMouseX = Input.mousePosition.x;
            startMouseY = Input.mousePosition.y;
        }
        // si no estamos presionando el botón izquierdo, y estamos arrastrando
        else if (Input.GetMouseButtonUp(0) && isDragging)
        {
            // establecer la bandera en falso
            isDragging = false;
        }
    }

    void LateUpdate()
    {
        // Comprueba si la estamos arrastrando
        if (isDragging)
        {
            //Calcular la posición actual del ratón

            float endMouseX = Input.mousePosition.x;
            float endMouseY = Input.mousePosition.y;

            //Difference (in screen coordinates)
            float diffX = endMouseX - startMouseX;
            float diffY = endMouseY - startMouseY;

            //Diferencia (en coordenadas de pantalla)
            float newCenterX = Screen.width / 2 + diffX;
            float newCenterY = Screen.height / 2 + diffY;

            //Obtener la coordenada mundial, aquí es donde queremos mirar
            Vector3 LookHerePoint = cam.ScreenToWorldPoint(new Vector3(newCenterX, newCenterY, cam.nearClipPlane));

            //Haz que nuestra cámara mire el "LookHerePoint"

            transform.LookAt(LookHerePoint);

            //posición inicial para la próxima llamada
            startMouseX = endMouseX;
            startMouseY = endMouseY;
        }
    }
}
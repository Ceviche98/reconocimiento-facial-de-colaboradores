# Reconocimiento facial de colaboradores usando Facenet y Siamese Networks


## Problematica

Actualmente existen modelos de clasificación con gran rendimiento. Esto se da en base al entrenamiento con grandes cantidades de datos y clases definidas. La situación se complica cuando se requiere agregar nuevas clases a las ya existentes. El modelo requerirá gran cantidad de datos de las nuevas clases y volver a entrenarse con el objetivo de ajustar sus pesos. El aprendizaje "One Shot" aparece para mitigar este problema porque puede realizar predicciones con solo un ejemplo de cada nueva clase. La idea es entrenar un modelo que aprenda a diferenciar entre distintas imagenes.

## Estado del arte 

### Facenet
FaceNet es una red neuronal que aprende un mapeo de imágenes faciales a un espacio euclidiano compacto, donde las distancias corresponden a una medida de similitud de caras. Entonces, cuanto más similares sean las dos imágenes faciales, menor será la distancia entre ellas. El método de Triplet Loss fue introducido por FaceNet para la tarea de reconocimiento de rostros, donde los autores proponen un nuevo enfoque en el entrenamiento de redes neuronales siamesas que permitan discriminar si dado 2 imágenes de rostros, estos pertenecen a la misma persona. Triplet Loss optimiza el espacio de búsqueda de tal manera que la entidades del mismo tipo se mantienen cercanos y al mismo tiempo entidades de diferente tipo se mantienen alejados. El concepto de Triplet Loss se exprea muy bien en la siguiente imagen.

![alt text](https://github.com/vcarlosrb/reconocimiento-facial-de-colaboradores/blob/master/Implementacion%20del%20sistema/assets/triplet_loss_function.png?raw=true)


### Siamese Network
La arquitectura de las Redes Siamesas contiene dos subredes convolucionales que poseen los mismos pesos teniendo imágenes de entrada diferentes. Luego de la última capa convolucional de cada subred, se transforma la capa a un solo vector. Por último, se calcula la distancia entre los vectores de salida de cada subred y este vector de distancia pasa a una unidad sigmoidal. Las Redes Siamesas son muy útiles, ya que aprender a diferenciar imágenes en lugar de aprender a clasificar. Además, las dos subredes comparten parámetros por lo que hay una menor tendencia a tener overfitting.


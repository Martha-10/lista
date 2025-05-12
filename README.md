inventario = [
    {'codigo': '001', 'nombre': 'Manzanas', 'cantidad': 50, 'precio': 0.5},
    {'codigo': '002', 'nombre': 'Bananas', 'cantidad': 30, 'precio': 0.3},
    # ... otros productos
]
def agregar_producto():
    codigo = input("Ingrese el código del producto: ")
    # Verificar si el código ya existe
    for producto in inventario:
        if producto['codigo'] == codigo:
            print("El producto ya existe.")
            return
    nombre = input("Ingrese el nombre del producto: ")
    cantidad = int(input("Ingrese la cantidad: "))
    precio = float(input("Ingrese el precio: "))
    nuevo_producto = {'codigo': codigo, 'nombre': nombre, 'cantidad': cantidad, 'precio': precio}
    inventario.append(nuevo_producto)
    print("Producto agregado exitosamente.")
    
def mostrar_inventario():
    if not inventario:
        print("El inventario está vacío.")
        return
    print("\nInventario:")
    print("{:<10} {:<15} {:<10} {:<10}".format('Código', 'Nombre', 'Cantidad', 'Precio'))
    for producto in inventario:
        print("{:<10} {:<15} {:<10} {:<10.2f}".format(
            producto['codigo'], producto['nombre'], producto['cantidad'], producto['precio']))

def actualizar_producto():
    codigo = input("Ingrese el código del producto a actualizar: ")
    for producto in inventario:
        if producto['codigo'] == codigo:
            nombre = input("Ingrese el nuevo nombre del producto: ")
            cantidad = int(input("Ingrese la nueva cantidad: "))
            precio = float(input("Ingrese el nuevo precio: "))
            producto['nombre'] = nombre
            producto['cantidad'] = cantidad
            producto['precio'] = precio
            print("Producto actualizado exitosamente.")
            return
    print("Producto no encontrado.")
    
def eliminar_producto():
    codigo = input("Ingrese el código del producto a eliminar: ")
    for producto in inventario:
        if producto['codigo'] == codigo:
            inventario.remove(producto)
            print("Producto eliminado exitosamente.")
            return
    print("Producto no encontrado.")

  def menu():
    while True:
        print("\n--- Sistema de Inventario ---")
        print("1. Agregar producto")
        print("2. Mostrar inventario")
        print("3. Actualizar producto")
        print("4. Eliminar producto")
        print("5. Salir")
        opcion = input("Seleccione una opción: ")

        if opcion == '1':
            agregar_producto()
        elif opcion == '2':
            mostrar_inventario()
        elif opcion == '3':
            actualizar_producto()
        elif opcion == '4':
            eliminar_producto()
        elif opcion == '5':
            print("Saliendo del sistema.")
            break
        else:
            print("Opción no válida. Intente nuevamente.")
            
if __name__ == "__main__":
    menu()



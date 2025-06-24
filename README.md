stokbook=[]
listaopcion=[1,2,3,4]
listadescripcion=["Ingresar libro","Buscar libro","Eliminar libro","Salir"]

def menu():
    print(f"{listaopcion[0]}.-{listadescripcion[0]}.")
    print(f"{listaopcion[1]}.-{listadescripcion[1]}.")
    print(f"{listaopcion[2]}.-{listadescripcion[2]}.")
    print(f"{listaopcion[3]}.-{listadescripcion[3]}.")

def Ingresar_libro(stokbook):
 try:
    titulolibro=input("Ingrese el titulo de un libro")
    for page in stokbook:
     while page["titulo"] == titulolibro:
      print("ya existe un titulo igual")
      titulolibro=input("Ingrese el titulo de un libro").strip()

    autorlibro=input("Ingrese el autor del libro")

    añolibro=int(input("Ingrese el año del libro"))
    while añolibro > 2025 or añolibro < 1500:
      print("el año no puede ser menor a 1500 ni año que ni siquiera an pasado al actual 2025")
      añolibro=int(input("Ingrese el año del libro"))

    book={"titulo":titulolibro,"autor":autorlibro,"año":añolibro}
    stokbook.append(book)
    print("registro exitoso")
 except TypeError and ValueError:
   print("error")

def Buscar_libro(stokbook):
 try:
    titulolibro=input("Ingrese el titulo del libro")
    for page in stokbook:
     if page["titulo"] == titulolibro:
        print(f"El libro titulado {page["titulo"]}- su autor es {page["autor"]}- su año de emision es {page["año"]}")
     else:
        print("no existe ese titulo de libro")
 except:
    print("error")

def Eliminar_libro(stokbook):
 try:
     titulo_libro=input("Ingrese el titulo del libro")
     for page in stokbook:
       if page["titulo"] == titulo_libro:
          stokbook.remove(page)
          print("libro eliminado")
       else:
         print("el titulo del libro no existe")
 except:
    print("error")

while True:
 try:
    menu()
 
    seleccion=int(input("Seleccione una opcion:"))
    if seleccion == 1:
      Ingresar_libro(stokbook)
    elif seleccion == 2:
      Buscar_libro(stokbook)
    elif seleccion == 3:
      Eliminar_libro(stokbook)
    elif seleccion == 4:
      print("Gracias por tu trabajo, saliendo del trabajo")
      break
 except ValueError:
   print("opcion no valida")

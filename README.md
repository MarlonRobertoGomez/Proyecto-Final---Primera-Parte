public class Autor
{
    public int Id { get; set; }
    public string Nombre { get; set; }
    public string Nacionalidad { get; set; }
    public string Biografia { get; set; }
    public DateTime FechaNacimiento { get; set; }
    public string GeneroLiterario { get; set; }
    public bool EstaActivo { get; set; }
    public string Codigo { get; set; }

    public ICollection<Libro> Libros { get; set; }
}

public class Categoria
{
    public int Id { get; set; }
    public string Nombre { get; set; }
    public string Descripcion { get; set; }
    public string Codigo { get; set; }
    public bool Activa { get; set; }
    public string Clasificacion { get; set; }
    public string ImagenURL { get; set; }
    public string CreadoPor { get; set; }

    public ICollection<Libro> Libros { get; set; }
}

public class DetallePrestamo
{
    public int Id { get; set; }

    public int PrestamoId { get; set; }
    public Prestamo Prestamo { get; set; }

    public int LibroId { get; set; }
    public Libro Libro { get; set; }

    public DateTime FechaEntrega { get; set; }
    public bool Devuelto { get; set; }
    public string Observacion { get; set; }
    public string Estado { get; set; }
    public int Cantidad { get; set; }
}

public class Editorial
{
    public int Id { get; set; }
    public string Nombre { get; set; }
    public string Pais { get; set; }
    public string SitioWeb { get; set; }
    public string Telefono { get; set; }
    public string Correo { get; set; }
    public string Direccion { get; set; }
    public DateTime FechaRegistro { get; set; }

    public ICollection<Libro> Libros { get; set; }
}

public class Libro
{
    public int Id { get; set; }
    public string Titulo { get; set; }
    public string ISBN { get; set; }
    public int AnioPublicacion { get; set; }
    public string Edicion { get; set; }

    public int AutorId { get; set; }
    public Autor Autor { get; set; }

    public int CategoriaId { get; set; }
    public Categoria Categoria { get; set; }

    public int EditorialId { get; set; }
    public Editorial Editorial { get; set; }
}

public class Prestamo
{
    public int Id { get; set; }
    public int UsuarioId { get; set; }
    public Usuario Usuario { get; set; }
    public DateTime FechaPrestamo { get; set; }
    public DateTime FechaDevolucion { get; set; }
    public string Estado { get; set; }
    public string Observaciones { get; set; }
    public string Codigo { get; set; }
    public string AprobadoPor { get; set; }

    public ICollection<DetallePrestamo> Detalles { get; set; }
}

public class Reserva
{
    public int Id { get; set; }
    public int UsuarioId { get; set; }
    public Usuario Usuario { get; set; }
    public int LibroId { get; set; }
    public Libro Libro { get; set; }
    public DateTime FechaReserva { get; set; }
    public DateTime FechaExpiracion { get; set; }
    public string Estado { get; set; }
    public string Observaciones { get; set; }
    public bool Confirmada { get; set; }
}

public class Rol
{
    public int Id { get; set; }
    public string Nombre { get; set; }
    public string Descripcion { get; set; }
    public DateTime FechaCreacion { get; set; }
    public string CreadoPor { get; set; }
    public bool Activo { get; set; }
    public string Codigo { get; set; }
    public string NivelAcceso { get; set; }

    public ICollection<Usuario> Usuarios { get; set; }
}

public class UbicacionLibro
{
    public int Id { get; set; }
    public int LibroId { get; set; }
    public Libro Libro { get; set; }

    public string Estanteria { get; set; }
    public string Fila { get; set; }
    public string Columna { get; set; }
    public string Seccion { get; set; }
    public string CodigoQR { get; set; }
    public string Piso { get; set; }
    public string Area { get; set; }
}

public class Usuario
{
    public int Id { get; set; }
    public string Nombre { get; set; }
    public string Correo { get; set; }
    public string Telefono { get; set; }
    public string Direccion { get; set; }
    public string UsuarioLogin { get; set; }
    public string Contrasena { get; set; }

    public int RolId { get; set; }
    public Rol Rol { get; set; }
}

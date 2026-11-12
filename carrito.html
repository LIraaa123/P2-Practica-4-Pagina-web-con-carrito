// Obtener carrito desde localStorage
function obtenerCarrito() {
  return JSON.parse(localStorage.getItem("carritoMultimarca")) || [];
}

// Guardar carrito y actualizar contador del menú
function guardarCarrito(carrito) {
  localStorage.setItem("carritoMultimarca", JSON.stringify(carrito));
  actualizarContador();
}

// Actualizar el número de artículos en el navbar
function actualizarContador() {
  const carrito = obtenerCarrito();
  const totalArticulos = carrito.reduce((suma, item) => suma + item.cantidad, 0);
  const contador = document.getElementById("contador-carrito");
  if (contador) {
    contador.textContent = totalArticulos;
  }
}

// Mostrar aviso visual al agregar un producto
function mostrarNotificacion(mensaje) {
  let toast = document.getElementById("toast");
  if (!toast) {
    toast = document.createElement("div");
    toast.id = "toast";
    document.body.appendChild(toast);
  }
  toast.textContent = mensaje;
  toast.className = "mostrar";
  setTimeout(() => {
    toast.className = toast.className.replace("mostrar", "");
  }, 2500);
}

// Agregar producto leyendo los datos directamente de la tarjeta HTML
function agregarDesdeTarjeta(boton) {
  const card = boton.closest(".card");
  const imagen = card.querySelector("img").src;
  const marca = card.querySelector(".brand").textContent.trim();
  const nombre = card.querySelector("h3").textContent.trim();
  const precioTexto = card.querySelector(".price").textContent;
  const precio = parseFloat(precioTexto.replace(/[^0-9.]/g, ""));

  const carrito = obtenerCarrito();
  const existente = carrito.find(
    (item) => item.nombre === nombre && item.marca === marca
  );

  if (existente) {
    existente.cantidad += 1;
  } else {
    carrito.push({ nombre, marca, precio, imagen, cantidad: 1 });
  }

  guardarCarrito(carrito);
  mostrarNotificacion(`✔ "${nombre}" agregado al carrito`);
}

// Renderizar la tabla dentro de carrito.html
function renderizarCarrito() {
  const contenedor = document.getElementById("contenido-carrito");
  if (!contenedor) return;

  const carrito = obtenerCarrito();

  if (carrito.length === 0) {
    contenedor.innerHTML = `
      <div class="carrito-vacio">
        <h2>Tu carrito está vacío</h2>
        <p>Explora nuestras categorías y agrega tus productos favoritos.</p>
        <a href="index.html" class="btn-agregar" style="display:inline-block; width:auto; text-decoration:none; margin-top:10px;">Ir a la tienda</a>
      </div>
    `;
    return;
  }

  let totalGeneral = 0;
  let filasHTML = "";

  carrito.forEach((item, index) => {
    const subtotal = item.precio * item.cantidad;
    totalGeneral += subtotal;

    filasHTML += `
      <tr>
        <td><img src="${item.imagen}" alt="${item.nombre}"></td>
        <td><strong>${item.marca}</strong></td>
        <td>${item.nombre}</td>
        <td>$${item.precio.toLocaleString("es-MX")} MXN</td>
        <td>
          <button class="btn-cantidad" onclick="cambiarCantidad(${index}, -1)">-</button>
          <span style="margin: 0 10px; font-weight: bold;">${item.cantidad}</span>
          <button class="btn-cantidad" onclick="cambiarCantidad(${index}, 1)">+</button>
        </td>
        <td><strong>$${subtotal.toLocaleString("es-MX")} MXN</strong></td>
        <td><button class="btn-eliminar" onclick="eliminarProducto(${index})">Eliminar</button></td>
      </tr>
    `;
  });

  contenedor.innerHTML = `
    <table class="tabla-carrito">
      <thead>
        <tr>
          <th>Imagen</th>
          <th>Marca</th>
          <th>Producto</th>
          <th>Precio Unitario</th>
          <th>Cantidad</th>
          <th>Subtotal</th>
          <th>Acción</th>
        </tr>
      </thead>
      <tbody>
        ${filasHTML}
      </tbody>
    </table>

    <div class="resumen-carrito">
      <div class="total-texto">Total a Pagar: <span>$${totalGeneral.toLocaleString("es-MX")} MXN</span></div>
      <div class="acciones-carrito">
        <button class="btn-vaciar" onclick="vaciarCarrito()">Vaciar Carrito</button>
        <button class="btn-pagar" onclick="finalizarCompra(${totalGeneral})">Finalizar Compra</button>
      </div>
    </div>
  `;
}

function cambiarCantidad(index, cambio) {
  const carrito = obtenerCarrito();
  carrito[index].cantidad += cambio;
  if (carrito[index].cantidad <= 0) {
    carrito.splice(index, 1);
  }
  guardarCarrito(carrito);
  renderizarCarrito();
}

function eliminarProducto(index) {
  const carrito = obtenerCarrito();
  carrito.splice(index, 1);
  guardarCarrito(carrito);
  renderizarCarrito();
}

function vaciarCarrito() {
  if (confirm("¿Seguro que deseas vaciar todo el carrito?")) {
    guardarCarrito([]);
    renderizarCarrito();
  }
}

function finalizarCompra(total) {
  const carrito = obtenerCarrito();
  const folio = "TM-" + Math.floor(100000 + Math.random() * 900000);
  const resumen = carrito
    .map((i) => `• ${i.cantidad}x ${i.nombre} (${i.marca})`)
    .join("\n");

  alert(
    `¡Compra realizada con éxito!\n\nFolio de pedido: ${folio}\nProductos:\n${resumen}\n\nTotal pagado: $${total.toLocaleString("es-MX")} MXN`
  );

  guardarCarrito([]);
  renderizarCarrito();
}

// Inicializar al cargar cualquier página
document.addEventListener("DOMContentLoaded", () => {
  actualizarContador();
  renderizarCarrito();
});

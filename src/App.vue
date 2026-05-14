<script setup>
import { ref, computed } from 'vue'

const categoriaSeleccionada = ref('Todos')
const articuloSeleccionado = ref(null);
const nombreBlog = ref("Gerencia de Operaciones")
const articulos = ref([
  { 
    id: 1, 
    titulo: "Conceptos Básicos", 
    resumen: "Explora los pilares de la producción y la transformación inteligente.",
    informacion: `En todo centro de informática existe el área de operaciones la cual es la encargada de administrar, manipular y operar los recursos físicos (hardware) y lógicos (software) a través de la puesta en marcha de los sistemas y datos que serán llevados a cabo en los equipos que posee. La gerencia de operaciones en un centro de informática que no se limita únicamente al mantenimiento de hardware; es el motor que garantiza que los servicios digitales se entreguen de manera eficiente, confiable y escalable.
    
    En el contexto de un centro de cómputo o unidad de TI, las operaciones representan el conjunto de actividades diarias necesarias para mantener el entorno tecnológico funcionando según las expectativas del negocio.

    <img src="https://images.unsplash.com/photo-1518770660439-4636190af475?auto=format&fit=crop&w=800" class="inline-info-image" alt="Centro de Datos y Servidores">

    <strong>1. Sistema de Producción Informática:</strong> Se refiere al proceso de transformar insumos (datos, solicitudes de usuarios, energía, talento humano) en productos o servicios (reportes, aplicaciones web, procesamiento de transacciones, soporte técnico).

    <strong>2. Capacidad de Procesamiento:</strong> Es el límite máximo de trabajo que un centro de informática puede manejar en un periodo determinado.
    En infraestructura: Se mide en términos de CPU, memoria RAM, almacenamiento y ancho de banda.
    En servicios: Se mide por el número de transacciones por segundo o usuarios concurrentes que el sistema puede soportar antes de degradarse.

    <strong>3. Disponibilidad y Continuidad:</strong> Es la garantía de que los sistemas estén operativos cuando los usuarios los necesiten.
    Disponibilidad: Generalmente medida en porcentajes (ej. 99.9%).
    Continuidad: Capacidad de recuperar la operación ante desastres (planes de contingencia y respaldos).

    <img src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?auto=format&fit=crop&w=800" class="inline-info-image" alt="Monitoreo de Sistemas">

    <strong>4. Ciclo de Vida de las Operaciones:</strong> Las operaciones no son estáticas; siguen un flujo constante que incluye:
    Planificación: Anticipar la demanda de recursos.
    Ejecución: El procesamiento real de los datos y ejecución de scripts.
    Monitoreo: Supervisar el rendimiento de los servidores y redes en tiempo real.
    Control: Corregir desviaciones (errores de software, caídas de red).

    <strong>5. Eficiencia vs. Eficacia Operativa: </strong>
    Eficacia: Lograr que el sistema haga lo que se supone que debe hacer (ej. que la base de datos entregue la información correcta).
    Eficiencia: Lograr el resultado utilizando la menor cantidad de recursos posibles (ej. optimizar una consulta SQL para que consuma menos CPU).

    <strong>6. Gestión de Niveles de Servicio (SLA):</strong>
    Es el compromiso formal entre el centro de informática y sus clientes (internos o externos). Define parámetros como el tiempo de respuesta ante fallas y el horario de operación de los sistemas.`,
    categoria: "Fundamentos",
    imagen: "https://images.unsplash.com/photo-1581091226825-a6a2a5aee158?auto=format&fit=crop&w=500"
  },
  { 
    id: 2, 
    titulo: "Funciones Críticas", 
    resumen: "¿Por qué la gestión de operaciones es el motor de la competitividad?",
    informacion: `Es fundamental abordar la gerencia de operaciones no solo como "mantenimiento", sino como una disciplina estratégica. En un centro de informática, las funciones de esta área aseguran que la tecnología se traduzca en resultados de negocio.
    
    Funciones de la Gerencia de Operaciones y Producción:
    
    <strong>1. Planificación y Control de la Producción:</strong>
    Esta función es el cerebro del área. Se encarga de determinar el "qué", "cuándo" y "con qué" se realizarán los procesos informáticos. Consiste en programar las tareas de procesamiento (batch processing), la ejecución de scripts y la generación de reportes masivos.
    Alcance: Incluye la previsión de la demanda (forecasting) para evitar cuellos de botella en fechas críticas (como cierres de mes o periodos de inscripción) y la asignación eficiente de prioridades a los distintos procesos de negocio.

    <img src="https://images.unsplash.com/photo-1451187580459-43490279c0fa?auto=format&fit=crop&w=800" class="inline-info-image" alt="Infraestructura de Red y Virtualización">

    <strong>2. Gestión de la Infraestructura y Plataforma:</strong>
    Es la función responsable de garantizar que el soporte físico y lógico (servidores, redes, almacenamiento, sistemas operativos) sea robusto y escalable. Su objetivo es que el "suelo" donde corren las aplicaciones sea estable.
    Alcance: Supervisa la virtualización, la salud de los centros de datos (climatización, energía) y la optimización de los recursos de hardware para maximizar el retorno de inversión tecnológica.

    <strong>3. Administración de la Disponibilidad y Continuidad:</strong>
    Su misión es eliminar los puntos de falla únicos. Esta función diseña y opera los mecanismos que permiten que el centro de informática siga funcionando incluso ante incidentes graves.
    Alcance: Implementación de arquitecturas de alta disponibilidad (clústeres), gestión de réplicas en tiempo real y, crucialmente, la ejecución y prueba periódica de los Planes de Recuperación ante Desastres (DRP). No se trata solo de tener respaldos, sino de garantizar que el tiempo de recuperación (RTO) sea el mínimo posible.

    <strong>¿Qué pasa cuando esto falla?</strong>

    <img src="https://images.unsplash.com/photo-1436491865332-7a61a109cc05?auto=format&fit=crop&w=800" class="inline-info-image" alt="Aviones en Aeropuerto - Caso Delta Airlines">

    <strong>El caso de Delta Airlines (2016):</strong>
    Un apagón en el centro de datos principal de Delta en Atlanta provocó la cancelación de más de 2,000 vuelos durante tres días.
    Esto pasa, porque aunque tenían respaldos, el Plan de Recuperación ante Desastres (DRP) falló al no poder realizar la transición a los sistemas secundarios de forma rápida. Esto demuestra que la función de continuidad no es solo "hacer copias", sino garantizar que el sistema pueda volver a la vida en minutos.

    <img src="https://images.unsplash.com/photo-1526374965328-7f61d4dc18c5?auto=format&fit=crop&w=800" class="inline-info-image" alt="Seguridad Informática y Hackeo">

    <strong>El hackeo a través de una pecera:</strong>
    En un casino de Las Vegas, unos atacantes ingresaron a la red interna a través del termostato inteligente de una pecera que estaba conectada al Wi-Fi.
    Esto ilustra la función de Seguridad Operativa. Los gerentes de operaciones deben vigilar cada dispositivo (IoT) que se conecta a la infraestructura, ya que cualquier punto descuidado es una puerta de entrada a la producción de datos sensibles.

    <strong>El error de configuración de Facebook (2021):</strong>
    En octubre de 2021, Facebook, Instagram y WhatsApp desaparecieron de internet por 6 horas debido a un error en la configuración de los protocolos de enrutamiento (BGP).
    Este caso explica la importancia del Monitoreo y Control de Cambios. Un pequeño ajuste manual en la infraestructura central puede desconectar a medio planeta si no existen procesos de validación y monitoreo de red en tiempo real.`,
    categoria: "Gestión",
    imagen: "https://images.unsplash.com/photo-1460925895917-afdab827c52f?auto=format&fit=crop&w=500"
  },
  { 
    id: 3, 
    titulo: "Importancia Estratégica", 
    resumen: "Diseño de procesos, manejo de inventarios y control de calidad",
    informacion: `En la era digital, si los sistemas se detienen, la empresa deja de existir. La importancia de esta área radica en su capacidad para construir una infraestructura resiliente. No se trata solo de evitar caídas, sino de asegurar que, ante un incidente (un ciberataque, un desastre natural o un fallo de hardware), la organización pueda recuperarse en el menor tiempo posible, minimizando pérdidas económicas que podrían ser catastróficas.

    <img src="https://images.unsplash.com/photo-1543286386-2e659306cd6c?auto=format&fit=crop&w=800" class="inline-info-image" alt="Gráficos de Optimización y Retorno de Inversión">

    <strong>Optimización y Retorno de Inversión (ROI):</strong>
    La tecnología es costosa. Una gerencia de operaciones eficiente asegura que cada servidor, cada licencia de software y cada terabyte de almacenamiento se utilice al máximo. Al evitar el "subaprovechamiento" de recursos y optimizar los procesos de producción, el área de operaciones transforma un centro de costos en una unidad de eficiencia, permitiendo que la inversión en TI rinda frutos reales.

    <strong>Pilar de la Experiencia del Usuario y la Reputación:</strong>
    La lealtad de un cliente hoy en día se mide en milisegundos. Si una aplicación es lenta o falla constantemente, el usuario se va a la competencia. La importancia de esta gerencia reside en mantener la calidad del servicio de cara al cliente final. Una operación impecable construye una reputación de confianza y profesionalismo, mientras que una operación deficiente puede destruir años de construcción de marca en cuestión de horas.

    <img src="https://images.unsplash.com/photo-1573164713988-8665fc963095?auto=format&fit=crop&w=800" class="inline-info-image" alt="Trabajo en equipo y Cumplimiento">

    <strong>Seguridad y Cumplimiento Legal:</strong>
    Vivimos en un mundo de regulaciones estrictas sobre la protección de datos. La Gerencia de Operaciones es la encargada de ejecutar las políticas de seguridad en el "mundo real". Su importancia es crítica para evitar brechas de datos que no solo resultan en multas legales masivas, sino en la pérdida total de confianza por parte de los socios y clientes.

    <strong>Facilitadora de la Innovación (Agilidad Operativa)</strong>
    Para que un equipo de desarrollo pueda lanzar nuevas funciones (como una nueva herramienta en una app), necesita una base operativa sólida y flexible. Una buena gestión de operaciones permite que la empresa sea ágil; si la infraestructura está bien administrada, es fácil escalar y adoptar nuevas tecnologías como Inteligencia Artificial o Big Data sin que el sistema actual colapse.`,
    categoria: "Estratégica",
    imagen: "https://images.unsplash.com/photo-1504384308090-c894fdcc538d?auto=format&fit=crop&w=500"
  }
])

// Función para abrir el modal
const abrirArticulo = (articulo) => {
  articuloSeleccionado.value = articulo;
};

// Función para cerrar el modal
const cerrarArticulo = () => {
  articuloSeleccionado.value = null;
};

const postsFiltrados = computed(() => {
  if (categoriaSeleccionada.value === 'Todos') return articulos.value
  return articulos.value.filter(post => post.categoria === categoriaSeleccionada.value)
})
</script>

<template>
  <!-- Contenedor principal -->
  <div class="app-innovative-container">
    
    <header class="main-header">
      <h1>{{ nombreBlog }}</h1> 
    </header>

    <nav class="filtros-container">
      <button 
        v-for="cat in ['Todos', 'Fundamentos', 'Gestión', 'Estratégica']" 
        :key="cat"
        @click="categoriaSeleccionada = cat"
        :class="{ active: categoriaSeleccionada === cat }"
      >
        {{ cat }}
      </button>
    </nav>

    <main class="blog-grid">
      <article v-for="post in postsFiltrados" :key="post.id" class="elegant-card">
        
        <!-- 1. Imagen Principal (Dinámica) -->
        <img 
          :src="post.imagen" 
          :alt="post.titulo" 
          :class="['card-image', { 'image-expanded': categoriaSeleccionada !== 'Todos' }]"
        >
        
        <!-- 2. Contenido de la tarjeta (Título y Categoría) -->
        <span class="category-tag">{{ post.categoria }}</span>
        <h2>{{ post.titulo }}</h2>

        <!-- 3. Muestra el RESUMEN solo si estamos en "Todos" -->
        <p v-if="categoriaSeleccionada === 'Todos'">
          {{ post.resumen }}
        </p>

        <!-- 4. Muestra la INFORMACIÓN LARGA (con imágenes) si NO estamos en "Todos" -->
        <div v-else class="full-info" v-html="post.informacion"></div>

        <!-- 5. Muestra el BOTÓN solo si estamos en "Todos" -->
        <button 
          v-if="categoriaSeleccionada === 'Todos'" 
          class="action-button" 
          @click="abrirArticulo(post)"
        >
          Leer artículo
        </button>

      </article>
    </main>

    <!-- Ventana Emergente (Modal) -->
    <div v-if="articuloSeleccionado" class="modal-overlay" @click="cerrarArticulo">
      <div class="modal-content" @click.stop>
        <button class="close-button" @click="cerrarArticulo">×</button>
        <img :src="articuloSeleccionado.imagen" class="modal-image">
        <span class="category-tag">{{ articuloSeleccionado.categoria }}</span>
        <h2 class="modal-title">{{ articuloSeleccionado.titulo }}</h2>
        <div class="modal-body">
          <div v-html="articuloSeleccionado.informacion"></div>
        </div>
      </div>
    </div>

  <footer class="footer">
  <hr />
  <p>© 2026 mi-blog. Todos los derechos reservados. Desarrollado por <strong>Oriana Ascanio</strong></p>
</footer>

  </div> 
</template>

<style scoped>
/* Base y Tipografía Inter */
.app-innovative-container {
  font-family: 'Inter', sans-serif;
  background-color: #a6b5dc;
  min-height: 100vh;
  padding: 60px 20px;
  color: #000;
}

.main-header {
  text-align: center;
  margin-top: 40px;
  margin-bottom: 80px;
}

.main-header h1 {
  font-family: 'Playfair Display', serif !important;
  font-size: 4.0rem !important; 
  font-weight: 400 !important; 
  letter-spacing: -1px !important; 
  color: #000 !important;
  font-style: normal;
  margin-bottom: 40px;

  }
   
@media (max-width: 600px) {
  h1 {
    font-size: 2rem !important; /* Ajusta este número hasta que no se amontone */
    line-height: 1.2;
    text-align: center;
  }
}


/* Navegación de Filtros */
.filtros-container {
  display: flex;
  justify-content: center;
  gap: 8px;
  margin-bottom: 60px;
}

.filtros-container button {
  background: transparent;
  border: 1px solid transparent;
  color: #666;
  padding: 6px 14px;
  border-radius: 6px;
  font-size: 0.9rem;
  cursor: pointer;
  transition: all 0.2s;
}

.filtros-container button:hover {
  background: #f0f0f0;
  color: #000;
}

.filtros-container button.active {
  background: #fff;
  color: #000;
  border-color: #eaeaea;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
  font-weight: 500;
}

/* Grid y Tarjetas */
.blog-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 30px;
  max-width: 1100px;
  margin: 0 auto;
}

.elegant-card p {
  padding-left: 25px;
  padding-right: 25px;
  color: #666;
  font-size: 0.95rem;
  line-height: 1.5;
  margin-bottom: 20px;
  flex-grow: 1; 
}

.elegant-card:hover {
  border-color: #000;
  box-shadow: 0 10px 20px rgba(0,0,0,0.04);
}

.category-tag {
  color: #0070f3;
  font-size: 0.7rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1px;
  display: block;
  margin-bottom: 12px;
}

.elegant-card h2 {
  font-family: 'Playfair Display', serif !important;
  font-size: 2rem !important; 
  font-weight: 500 !important; 
  color: #000;
  letter-spacing: 0.5px;
  margin-top: 5px;
  margin-bottom: 15px;
  text-transform: capitalize;

}


/* 1. Ajuste de la Tarjeta */
.elegant-card {
  background: #fff;
  padding: 0;
  border-radius: 12px;
  border: 1px solid #eaeaea;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  height: 100%;
  animation: fadeIn 0.5s ease backwards;
}

/* 2. Ajuste de la Imagen base */
.card-image {
  width: 100%;
  height: 220px;
  object-fit: cover;
  object-position: center;
  margin-bottom: 20px;
  transition: height 0.3s ease; 
}

/* 3. Clase que se activa al filtrar */
.image-expanded {
  height: 400px !important; 
}

/* ESTILOS PARA LAS IMÁGENES INTERCALADAS (NUEVO) */
:deep(.inline-info-image) {
  width: 100%;
  max-height: 280px;
  object-fit: cover;
  border-radius: 8px;
  margin: 25px 0;
  box-shadow: 0 4px 12px rgba(0,0,0,0.06);
  display: block;
}

/* 4. Ajuste del texto para que no toque los bordes */
.elegant-card h2, 
.elegant-card p, 
.elegant-card .category-tag,
.elegant-card .action-button,
.elegant-card .full-info {
  padding-left: 25px;
  padding-right: 25px;
}

.action-button {
  margin: 0 25px 25px 25px;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  border-radius: 6px;
  cursor: pointer;
  align-self: stretch; 
  text-align: center;
}

.action-button:hover {
  background: transparent;
  color: #000;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

/* Ventana Modal */
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
  padding: 20px;
}

.modal-content {
  background: white;
  width: 100%;
  max-width: 700px;
  max-height: 90vh;
  border-radius: 15px;
  position: relative;
  overflow-y: auto; 
  padding: 30px;
  animation: modalIn 0.3s ease-out;
}

@keyframes modalIn {
  from { transform: translateY(20px); opacity: 0; }
  to { transform: translateY(0); opacity: 1; }
}

.modal-image {
  width: 100%;
  height: 300px;
  object-fit: cover;
  border-radius: 10px;
  margin-bottom: 20px;
}

.modal-title {
  font-family: 'Playfair Display', serif !important;
  font-size: 2.5rem !important;
  margin: 15px 0;
  color: #000000 !important;
}

.close-button {
  position: absolute;
  top: 15px;
  right: 20px;
  font-size: 2rem;
  background: none;
  border: none;
  cursor: pointer;
  color: #666;
}

.modal-body p {
  font-size: 1.1rem;
  line-height: 1.7;
  color: #333;
  white-space: pre-line;
  .modal-body div {
  text-align: justify;
  text-justify: inter-word;
}
}

.full-info {
  font-size: 0.95rem;
  line-height: 1.7;
  color: #444;
  white-space: pre-line; 
  margin-bottom: 25px;
  padding-bottom: 15px;
  text-align: justify;
  text-justify: inter-word; /* Mejora el espaciado entre palabras */
  hyphens: auto;
}

.footer {
  text-align: center;
  padding: 20px;
  background-color: #526386; 
  color: #f1ebeb; 
}
.footer hr {
  border: 0;
  border-top: 1px solid #596378;
  margin-bottom: 20px;
}
</style>
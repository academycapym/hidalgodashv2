import React, { useState, useEffect, useMemo, useRef } from 'react';
import { Upload, Filter, RefreshCw, AlertCircle, CheckCircle2, Search, LogOut, Smartphone, User, Lock, Store, TrendingUp, Package, ChevronDown, ChevronUp, Layers, FileText, BookOpen, Users, Trophy, Award, Clock, Calendar, CheckSquare, XCircle, Camera, Edit2, Star, Target, MapPin, Activity, Check, Download, Trash2, Eye } from 'lucide-react';
import { initializeApp } from 'firebase/app';
import { getAuth, signInAnonymously, onAuthStateChanged, signInWithCustomToken } from 'firebase/auth';
import { getFirestore, doc, setDoc, onSnapshot, collection, deleteDoc } from 'firebase/firestore';

// ============================================================================
// CONFIGURACIÓN DE FIREBASE
// ============================================================================
const getFirebaseConfig = () => {
  if (typeof __firebase_config !== 'undefined') {
    return JSON.parse(__firebase_config);
  }
  return {
    apiKey: process.env.REACT_APP_FIREBASE_API_KEY || "tu_api_key",
    authDomain: process.env.REACT_APP_FIREBASE_AUTH_DOMAIN || "tu_auth_domain",
    projectId: process.env.REACT_APP_FIREBASE_PROJECT_ID || "tu_project_id",
    storageBucket: process.env.REACT_APP_FIREBASE_STORAGE_BUCKET || "tu_storage_bucket",
    messagingSenderId: process.env.REACT_APP_FIREBASE_MESSAGING_SENDER_ID || "tu_messaging_sender",
    appId: process.env.REACT_APP_FIREBASE_APP_ID || "tu_app_id"
  };
};

const app = initializeApp(getFirebaseConfig());
const auth = getAuth(app);
const db = getFirestore(app);
const APP_ID = typeof __app_id !== 'undefined' ? __app_id : 'hidalgo-dash-app';

// ============================================================================
// DATOS DE EXÁMENES (PREGUNTAS AMPLIADAS - SIN DN TRANSITORIO)
// ============================================================================
const EXAM_DATA = {
  portabilidad: {
    id: 'portabilidad',
    title: 'Portabilidad Básica',
    category: 'Nuevo Ingreso',
    questions: [
      { q: "Contexto: Un cliente llega a tu punto de venta interesado en mantener su número actual pero cambiando a los beneficios de Movistar. Según el manual oficial, ¿cuál es la definición y el propósito fundamental del proceso de Portabilidad?", options: ["Un trámite con costo para actualizar el chip a tecnología 5G.", "Un proceso muy sencillo que permite a una persona física cambiarse de compañía telefónica conservando su número móvil.", "El proceso de cambiar una línea de esquema prepago a un plan tarifario (pospago).", "La transferencia de saldo y contactos entre dos equipos telefónicos diferentes."], a: 1 },
      { q: "Contexto: Para iniciar el trámite, el cliente necesita generar un NIP de confirmación que valide su identidad como dueño de la línea. ¿A qué número específico debe enviar un mensaje de texto (SMS) desde su chip actual para recibir este código?", options: ["Enviando la palabra ALTA al 071.", "Llamando directamente al *611 y hablando con un asesor.", "Enviando la palabra NIP al número 051.", "Enviando su CURP por mensaje de texto al 01800."], a: 2 },
      { q: "Contexto: Has generado exitosamente el NIP para la portabilidad de tu cliente. Para evitar que el trámite sea rechazado por caducidad en el sistema, ¿cuál es el tiempo exacto de vigencia que tiene este NIP desde el momento de su emisión?", options: ["24 horas hábiles.", "15 días laborables.", "3 días naturales.", "5 días naturales."], a: 3 },
      { q: "Contexto: Al realizar el proceso bajo la modalidad de 'Persona Física', existen requisitos obligatorios para evitar fraudes. ¿Quién es la única persona autorizada para solicitar la portabilidad y qué debe presentar?", options: ["Cualquier familiar directo presentando su propia identificación.", "El vendedor a nombre del cliente usando su código de empleado.", "Únicamente el suscriptor o titular de la línea presentando una identificación oficial.", "El distribuidor mayorista mediante una carta poder."], a: 2 },
      { q: "Contexto: Un cliente de tipo 'Persona Moral' (empresa) desea portar su número a Movistar bajo la modalidad de Persona Física para agilizar el papeleo. Según las normativas, ¿qué ocurrirá con esta solicitud al ser evaluada?", options: ["La solicitud será rechazada automáticamente al no coincidir el tipo de persona.", "Se le cobrará una penalización económica al cliente.", "Pasará directamente sin problemas si el NIP es correcto.", "Requerirá que el cliente genere un segundo NIP de seguridad."], a: 0 },
      { q: "Contexto: Una vez ingresados los datos en la App y aprobado el trámite, el cambio de red se ejecuta de forma automática para no interrumpir el día del cliente. ¿En qué ventana de horario máxima se realiza técnicamente esta transición de línea?", options: ["Entre las 6:00 am y las 8:00 am.", "Inmediatamente después de la firma.", "Entre las 12:00 am y la 1:00 am.", "Entre las 2:00 am y las 3:30 am."], a: 3 },
      { q: "Contexto: Estás explicando el proceso a un prospecto que tiene mucha prisa y te pregunta sobre el tiempo de resolución. Considerando que la línea está activa, ¿cuánto tiempo mínimo tarda en concluir todo el proceso de portabilidad?", options: ["Mínimo 2 horas.", "Mínimo 24 horas.", "Mínimo 5 días hábiles.", "Mínimo 48 horas."], a: 1 },
      { q: "Contexto: Dentro del vocabulario técnico que utilizamos, a menudo leemos las siglas 'ABD' cuando un trámite está en validación. ¿Qué significan estas siglas y cuál es su rol?", options: ["Administrador de Base de Datos, que es el organismo central que regula el proceso.", "Agente de Búsqueda de Datos, encargado de validar el RFC.", "Asignación Básica Directa, el sistema de Movistar.", "Almacenamiento de Banda Dual, referente a la tecnología del chip."], a: 0 },
      { q: "Contexto: Has ingresado el trámite en el sistema y el cliente pregunta cómo se enterará de la fecha exacta de su cambio. Según el proceso, ¿cómo y quién notifica al cliente sobre la Fecha de Ventana de Cambio (FVC) aceptada?", options: ["El vendedor debe llamarle personalmente al día siguiente para avisarle.", "El sistema le enviará un SMS automático confirmando que su trámite fue exitoso y detallando su FVC.", "Recibirá un correo electrónico formal por parte del ABD.", "Se le notificará por medio de una carta enviada a su domicilio."], a: 1 },
      { q: "Contexto: Durante la captura de los datos en la aplicación, la plataforma solicita registrar una clave para asegurar que la venta se te asigne correctamente. ¿A qué se refieren las siglas 'DI' en este paso?", options: ["Documento de Identidad.", "Día de Ingreso.", "Número que identifica al Distribuidor para el cual trabajas.", "Dígitos de Interconexión."], a: 2 },
    ]
  },
  sueldo_base: {
    id: 'sueldo_base', title: 'Sueldo Base y Condiciones', category: 'Nuevo Ingreso',
    questions: [
      { q: "Contexto: El nuevo esquema de pago establece métricas de tiempo estrictas para validar un día laboral. Para que un registro sea considerado apto para el pago, ¿cuál es el tiempo mínimo requerido que debe transcurrir entre tu Check-In y tu Check-Out?", options: ["300 minutos (5 horas).", "420 minutos (7 horas).", "500 minutos (8.3 horas).", "480 minutos (8 horas)."], a: 3 },
      { q: "Contexto: Durante tu jornada laboral tienes derecho a un tiempo destinado para tus alimentos. Según el comunicado vigente, ¿cuál es el rango de tiempo permitido para registrar tu salida y regreso de comer?", options: ["Exactamente 60 minutos.", "De 15 a 90 minutos.", "De 30 a 60 minutos.", "De 5 a 75 minutos."], a: 3 },
      { q: "Contexto: La puntualidad es monitoreada automáticamente. ¿Cuál es el bloque de horario matutino establecido oficialmente como válido para realizar tu Check-In (hora de entrada)?", options: ["De 08:30 a 12:00 hrs.", "De 09:30 a 12:30 hrs.", "De 08:00 a 10:00 hrs.", "De 09:00 a 11:00 hrs."], a: 1 },
      { q: "Contexto: Para que tu día sea contabilizado correctamente, ¿qué rango de horario vespertino es el válido para hacer tu Check-Out (salida)?", options: ["De 17:00 a 20:00 hrs.", "De 18:30 a 21:30 hrs.", "De 18:00 a 21:00 hrs.", "De 19:00 a 22:00 hrs."], a: 2 },
      { q: "Contexto: El sistema entiende que pueden presentarse ligeros contratiempos. ¿Cuál es el rango de tolerancia exacto para los horarios de Check-In y Check-Out?", options: ["15 minutos.", "10 minutos antes y 10 minutos después.", "5 minutos.", "No existe tolerancia."], a: 1 },
      { q: "Contexto: Si existen dos registros de venta utilizando el mismo IMEI en el mismo día, ¿qué procederá?", options: ["Se pagan dobles.", "Se bloquea la cuenta.", "Se restan de la cuota.", "Se descartan del conteo."], a: 3 },
      { q: "Contexto: ¿Cuál es el ÚNICO método oficial autorizado para iniciar una aclaración formal de nómina o comisiones?", options: ["Correo a RRHH.", "Levantar un ticket en los enlaces oficiales.", "WhatsApp al supervisor.", "Llamar a finanzas."], a: 1 },
      { q: "Contexto: ¿A partir de qué fecha específica entraron en vigor las nuevas consideraciones de checks válidos?", options: ["1 de enero 2025.", "15 de julio 2025.", "16 de junio 2025.", "2 de junio 2025."], a: 2 },
      { q: "Contexto: En caso de laborar en un PDV con horarios de apertura/cierre diferenciados, ¿cómo se valida la asistencia?", options: ["Deben apegarse al estándar.", "Se validan previamente con planificación.", "Tienen libertad de horario.", "Se les descuenta un %."], a: 1 },
      { q: "Contexto: ¿Qué criterio es indispensable para que el marcaje de asistencia no sea invalidado técnicamente?", options: ["Autorización del supervisor.", "Estar dentro del rango y tolerancia estipulados.", "Foto con el gerente.", "Conexión WiFi obligatoria."], a: 1 },
    ]
  },
  venta_consultiva: {
    id: 'venta_consultiva', title: 'Venta Consultiva', category: 'Nuevo Ingreso',
    questions: [
      { q: "Contexto: En la 'Fórmula Potenciadora de Ventas', ¿cuál es el factor más crítico para tener éxito?", options: ["Conocimiento técnico.", "Apariencia física.", "El Empuje (actitud y perseverancia).", "Habilidad de manipulación."], a: 2 },
      { q: "Contexto: ¿Cuáles son las tres consideraciones internas que motivan una decisión de compra?", options: ["Sociales, estatus y lujo.", "Inteligentes, Emocionales y Racionalizaciones.", "Rapidez, precio y calidad.", "Instinto, obligación y costo."], a: 1 },
      { q: "Contexto: ¿Qué es lo que realmente compra el cliente cuando adquiere un servicio?", options: ["Los Beneficios (lo que el producto hace por él).", "Especificaciones técnicas.", "El producto tangible.", "Ventajas competitivas."], a: 0 },
      { q: "Contexto: ¿Cuál es la proporción de tiempo ideal recomendada entre hablar y escuchar durante el sondeo?", options: ["Vendedor habla 80%.", "Vendedor habla 50%.", "Vendedor escucha 80%.", "El cliente solo responde Sí/No."], a: 2 },
      { q: "Contexto: Para neutralizar una objeción sin lastimar el ego del cliente, ¿qué fórmula se recomienda?", options: ["Atacar - Demostrar - Vencer.", "Negar - Ignorar - Persuadir.", "Siente - Sintieron - Se dieron cuenta.", "Ofrecer rebaja inmediata."], a: 2 },
      { q: "Contexto: ¿Con qué palabras clave deben iniciar las 'Preguntas Abiertas' para un sondeo efectivo?", options: ["¿Verdad que sí...?", "¿Me permite...?", "¿Está seguro...?", "¿Quién?, ¿Qué?, ¿Dónde?, ¿Cuándo?, ¿Cómo?, ¿Por qué?"], a: 3 },
      { q: "Contexto: El concepto del 'Análisis de la Brecha' (The Gap) se refiere a:", options: ["Diferencia económica.", "Diferencia entre situación actual (descontento) y situación ideal futura.", "Margen de ganancia.", "Distancia física al PDV."], a: 1 },
      { q: "Contexto: ¿Cuál es la definición correcta de la etapa de 'Cierre'?", options: ["Manipular al cliente.", "Acto natural de recabar la decisión tras completar bien los pasos previos.", "Presión psicológica máxima.", "Trucos mentales."], a: 1 },
      { q: "Contexto: En la 'Teoría ABC', ¿qué factor representa la letra 'A'?", options: ["Estado actual de descontento.", "Aceptación social.", "El producto vendido.", "Actitud del promotor."], a: 0 },
      { q: "Contexto: El 85% de la conducta de las personas está determinada por:", options: ["Experiencias pasadas.", "El precio inmediato.", "Nivel socioeconómico.", "Lo que anticipan que pasará como consecuencia futura."], a: 3 },
    ]
  }
};

const compressImage = (file, callback) => {
  const reader = new FileReader();
  reader.readAsDataURL(file);
  reader.onload = e => {
    const img = new Image();
    img.src = e.target.result;
    img.onload = () => {
      const canvas = document.createElement('canvas');
      const MAX_WIDTH = 150;
      const scaleSize = MAX_WIDTH / img.width;
      canvas.width = MAX_WIDTH;
      canvas.height = img.height * scaleSize;
      const ctx = canvas.getContext('2d');
      ctx.drawImage(img, 0, 0, canvas.width, canvas.height);
      callback(canvas.toDataURL('image/jpeg', 0.7)); 
    };
  };
};

export default function App() {
  const [firebaseUser, setFirebaseUser] = useState(null);
  const [dataOperacion, setDataOperacion] = useState([]);
  const [dataInventario, setDataInventario] = useState([]);
  const [lastUpdated, setLastUpdated] = useState('');
  const [loading, setLoading] = useState(true);

  const [rostersData, setRostersData] = useState([]);
  const [examResults, setExamResults] = useState([]);
  
  const [appUser, setAppUser] = useState(null); 
  const [loginForm, setLoginForm] = useState({ username: '', password: '' });
  const [loginError, setLoginError] = useState('');

  const [activeMainTab, setActiveMainTab] = useState('detalle_diario'); 
  const [activeSubTab, setActiveSubTab] = useState('operacion'); 
  const [activeAcademiaTab, setActiveAcademiaTab] = useState('examenes'); 
  
  const [uploadStatusOp, setUploadStatusOp] = useState({ type: '', message: '' });
  const [uploadStatusInv, setUploadStatusInv] = useState({ type: '', message: '' });
  const [scriptsLoaded, setScriptsLoaded] = useState(false);

  const [supervisorFilter, setSupervisorFilter] = useState('');
  const [cadenaFilter, setCadenaFilter] = useState('');
  const [estatusFilter, setEstatusFilter] = useState('');
  const [invSupervisorFilter, setInvSupervisorFilter] = useState('');
  const [invCadenaFilter, setInvCadenaFilter] = useState('');
  const [invMarcaFilter, setInvMarcaFilter] = useState('');
  const [invModeloFilter, setInvModeloFilter] = useState('');
  const [expandedStore, setExpandedStore] = useState(null);

  useEffect(() => {
    const scriptXlsx = document.createElement('script');
    scriptXlsx.src = "https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js";
    document.head.appendChild(scriptXlsx);

    const scriptPdf = document.createElement('script');
    scriptPdf.src = "https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js";
    document.head.appendChild(scriptPdf);
    scriptPdf.onload = () => setScriptsLoaded(true);

    const initAuth = async () => {
      try {
        if (typeof __initial_auth_token !== 'undefined' && __initial_auth_token) {
          await signInWithCustomToken(auth, __initial_auth_token);
        } else {
          await signInAnonymously(auth);
        }
      } catch (error) { console.error("Auth:", error); }
    };
    initAuth();
    const unsubscribe = onAuthStateChanged(auth, setFirebaseUser);
    return () => unsubscribe();
  }, []);

  useEffect(() => {
    if (!firebaseUser) return;
    const opRef = doc(db, 'artifacts', APP_ID, 'public', 'data', 'dashboard', 'operacion');
    onSnapshot(opRef, (snap) => {
      if (snap.exists()) {
        setDataOperacion(snap.data().stores || []);
        setLastUpdated(snap.data().lastUpdated || '');
      }
      setLoading(false);
    });
    const invRef = doc(db, 'artifacts', APP_ID, 'public', 'data', 'dashboard', 'inventario');
    onSnapshot(invRef, (snap) => { if (snap.exists()) setDataInventario(snap.data().items || []); });
    const rosterRef = collection(db, 'artifacts', APP_ID, 'public', 'data', 'rosters');
    onSnapshot(rosterRef, (snap) => {
      const rs = []; snap.forEach(d => rs.push({ id: d.id, ...d.data() }));
      setRostersData(rs);
    });
    const examsRef = collection(db, 'artifacts', APP_ID, 'public', 'data', 'examResults');
    onSnapshot(examsRef, (snap) => {
      const ex = []; snap.forEach(d => ex.push({ id: d.id, ...d.data() }));
      setExamResults(ex);
    });
  }, [firebaseUser]);

  const handleLogin = (e) => {
    e.preventDefault();
    setLoginError('');
    if (loginForm.username.toLowerCase() === 'admin' && loginForm.password === '2024') {
      setAppUser({ role: 'admin', uid: 'admin-user' });
      setActiveMainTab('detalle_diario');
    } else if (loginForm.password === 'movistar1' && loginForm.username.trim() !== '') {
      setAppUser({ role: 'pdv', idpdv: loginForm.username.trim(), uid: loginForm.username.trim() });
      setActiveMainTab('detalle_diario');
    } else {
      setLoginError('Usuario o contraseña incorrectos.');
    }
  };

  const handleFileUploadOperacion = (e) => { 
     const file = e.target.files[0];
     if (!file || !window.XLSX) return;
     setUploadStatusOp({ type: 'loading', message: 'Procesando...' });
     const reader = new FileReader();
     reader.onload = async (ev) => {
       try {
         const workbook = window.XLSX.read(new Uint8Array(ev.target.result), { type: 'array' });
         const sheet = workbook.Sheets[workbook.SheetNames.find(n => n.includes("Seg Diario")) || workbook.SheetNames[0]];
         const rows = window.XLSX.utils.sheet_to_json(sheet, { header: 1 });
         const stores = [];
         for (let i = 5; i < rows.length; i++) {
           const r = rows[i]; if (!r || !r[8]) continue;
           stores.push({ supervisor: r[1], estatus: r[7], idpdv: String(r[8]).trim(), nombre: r[9], cadena: r[11], altas: r[16]||0, cuota: r[17]||0, gap: r[18]||0, alcance: Math.round((r[15]||0)*100) });
         }
         await setDoc(doc(db, 'artifacts', APP_ID, 'public', 'data', 'dashboard', 'operacion'), { lastUpdated: new Date().toLocaleDateString(), stores, timestamp: new Date().toISOString() });
         setUploadStatusOp({ type: 'success', message: '¡Listo!' });
       } catch (error) { setUploadStatusOp({ type: 'error', message: 'Error' }); }
     };
     reader.readAsArrayBuffer(file);
  };

  const visibleStoresOp = useMemo(() => {
    if (!appUser) return [];
    if (appUser.role === 'pdv') return dataOperacion.filter(s => s.idpdv === appUser.idpdv);
    return dataOperacion.filter(s => (!supervisorFilter || s.supervisor === supervisorFilter) && (!cadenaFilter || s.cadena === cadenaFilter) && (!estatusFilter || s.estatus === estatusFilter));
  }, [dataOperacion, appUser, supervisorFilter, cadenaFilter, estatusFilter]);

  const summaryOperacion = useMemo(() => {
    let a=0, c=0, g=0; visibleStoresOp.forEach(s => { a+=s.altas; c+=s.cuota; g+=s.gap; });
    return { altasTotales: a, cuotaTotales: c, gapTotal: g, alcanceTotal: c>0 ? Math.round((a/c)*100) : 0 };
  }, [visibleStoresOp]);

  const AcademiaRosters = () => {
    const isRegistered = rostersData.find(r => r.uid === appUser.uid);
    const [formData, setFormData] = useState(isRegistered ? { ...isRegistered } : { uid: appUser.uid, idpdv: appUser.idpdv || 'ADMIN', nombre: '', usuarioFw: '', telefono: '', fechaIngreso: '', fechaNacimiento: '', supervisor: '', sexo: '', rol: 'promotor fijo', foto: '' });
    const handlePhoto = (e) => {
      const file = e.target.files[0];
      if (file) compressImage(file, b => setFormData({...formData, foto: b}));
    };
    const save = async (e) => {
      e.preventDefault();
      await setDoc(doc(db, 'artifacts', APP_ID, 'public', 'data', 'rosters', appUser.uid), { ...formData, timestamp: new Date().toISOString() });
    };
    if (appUser.role === 'pdv') {
      return (
        <div className="max-w-2xl mx-auto bg-white p-8 rounded-3xl shadow-sm border border-gray-100">
          <h2 className="text-2xl font-black text-[#0B2739] mb-6 flex items-center gap-3"><Users className="text-[#019DF4]"/>Mi Perfil</h2>
          <form onSubmit={save} className="space-y-6">
            <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
              <input placeholder="Nombre Completo" required disabled={isRegistered} value={formData.nombre} onChange={e=>setFormData({...formData, nombre: e.target.value})} className="border p-3 rounded-xl bg-gray-50"/>
              <input placeholder="Teléfono" required value={formData.telefono} onChange={e=>setFormData({...formData, telefono: e.target.value})} className="border p-3 rounded-xl"/>
            </div>
            <div className="flex items-center gap-4 border-t pt-4">
               {formData.foto ? <img src={formData.foto} className="w-20 h-20 rounded-full object-cover border-4 border-[#019DF4]"/> : <div className="w-20 h-20 bg-gray-100 rounded-full flex items-center justify-center"><User className="text-gray-400"/></div>}
               <label className="cursor-pointer bg-white border px-4 py-2 rounded-xl text-sm font-bold"><Camera className="inline w-4 h-4 mr-2"/>Cambiar Foto<input type="file" className="hidden" onChange={handlePhoto}/></label>
            </div>
            <button type="submit" className="w-full bg-[#5BC500] text-white font-black py-4 rounded-2xl shadow-lg">{isRegistered ? 'Actualizar Datos' : 'Registrarse'}</button>
          </form>
        </div>
      );
    }
    return <div className="bg-white p-6 rounded-3xl border border-gray-100"><h3 className="font-bold mb-4">Directorio Admin</h3><div className="overflow-x-auto"><table className="w-full text-left"><thead><tr className="text-xs text-gray-400 uppercase"><th>Promotor</th><th>Edad</th><th>Antigüedad</th></tr></thead><tbody>{rostersData.map(r => <tr key={r.id}><td>{r.nombre}</td><td>{Math.floor((new Date()-new Date(r.fechaNacimiento))/31557600000)} años</td><td>{Math.floor((new Date()-new Date(r.fechaIngreso))/(1000*60*60*24*30))} meses</td></tr>)}</tbody></table></div></div>;
  };

  const Certificate = ({ result, onClose }) => {
    const download = () => {
      const el = document.getElementById('cert-pdf');
      window.html2pdf().set({ margin:0, filename:'Certificado.pdf', image:{type:'jpeg',quality:1}, html2canvas:{scale:3}, jsPDF:{format:'a4',orientation:'landscape'} }).from(el).save();
    };
    return (
      <div className="fixed inset-0 z-50 bg-black/80 p-4 flex items-center justify-center overflow-y-auto">
        <div className="bg-white p-6 rounded-2xl flex flex-col items-center max-w-4xl w-full">
          <div id="cert-pdf" className="bg-white w-[800px] h-[565px] border-[16px] border-[#0B2739] p-12 text-center flex flex-col items-center justify-center">
            <h1 className="text-2xl font-black tracking-widest text-[#0B2739] mb-4">CERTIFICADO DE ACREDITACIÓN</h1>
            <p className="text-sm font-bold text-gray-500 mb-8">HidalgoDash y CAPYM otorgan el presente reconocimiento a:</p>
            <h2 className="text-4xl font-black text-[#019DF4] uppercase border-b-2 border-gray-200 pb-2 w-3/4 mb-10">{result.userName}</h2>
            <p className="text-sm text-gray-600 mb-2">Por haber concluido satisfactoriamente la certificación oficial en:</p>
            <h3 className="text-2xl font-black text-[#0B2739] uppercase mb-16">{result.examName}</h3>
            <div className="w-full flex justify-between items-end mt-auto px-12">
               <p className="text-xs font-bold text-gray-400">Emitido: {new Date(result.timestamp).toLocaleDateString()}</p>
               <div className="flex flex-col items-center"><div className="w-48 border-b-2 border-[#0B2739] mb-1"></div><p className="text-[10px] font-black">JUAN ROBERTO ESCALANTE CAMPOS</p><p className="text-[8px] font-bold text-gray-400 uppercase">GTE Regional Hidalgo</p></div>
            </div>
          </div>
          <div className="flex gap-4 mt-6">
            <button onClick={download} className="bg-[#019DF4] text-white px-6 py-3 rounded-xl font-black shadow-lg flex items-center gap-2"><Download/> Descargar PDF</button>
            <button onClick={onClose} className="bg-gray-100 px-6 py-3 rounded-xl font-bold">Cerrar</button>
          </div>
        </div>
      </div>
    );
  };

  const AcademiaExamenes = () => {
    const isRegistered = rostersData.find(r => r.uid === appUser.uid);
    const [activeQuiz, setActiveQuiz] = useState(null);
    const [currentQ, setCurrentQ] = useState(0);
    const [answers, setAnswers] = useState({});
    const [timeLeft, setTimeLeft] = useState(150);
    const [finished, setFinished] = useState(false);
    const [result, setResult] = useState(null);
    const [showCert, setShowCert] = useState(false);
    const [adminView, setAdminView] = useState('grid');

    const available = useMemo(() => {
      let l = Object.values(EXAM_DATA);
      if (appUser.role === 'pdv') {
        const cadena = dataOperacion.find(s=>s.idpdv===appUser.idpdv)?.cadena?.toLowerCase() || '';
        l = l.filter(ex => { if(ex.id==='comisiones_ekt' && !cadena.includes('elektra')) return false; if(ex.id==='comisiones_coppel' && cadena.includes('elektra')) return false; return true; });
      }
      return l;
    }, [dataOperacion, appUser]);

    useEffect(() => {
      if (activeQuiz && !finished && timeLeft > 0) { const t=setInterval(()=>setTimeLeft(p=>p-1), 1000); return ()=>clearInterval(t); }
      else if (timeLeft===0 && !finished && activeQuiz) finish();
    }, [activeQuiz, finished, timeLeft]);

    const start = (ex) => {
      if (appUser.role==='pdv' && !isRegistered) { setActiveAcademiaTab('rosters'); return; }
      setActiveQuiz(ex); setCurrentQ(0); setAnswers({}); setTimeLeft(150); setFinished(false);
    };

    const finish = async () => {
      setFinished(true); let c=0; activeQuiz.questions.forEach((q,i)=> { if(answers[i]===q.a) c++; });
      const p = c>=8; const score = c*10 + Math.floor(timeLeft/3);
      const res = { uid:appUser.uid, userName:isRegistered?isRegistered.nombre:appUser.uid, examId:activeQuiz.id, examName:activeQuiz.title, correct:c, totalQ:10, totalScore:score, passed:p, userAnswers:answers, timestamp:new Date().toISOString(), idpdv:appUser.idpdv||'ADMIN' };
      setResult(res); if(p) setTimeout(()=>setShowCert(true), 800);
      await setDoc(doc(db, 'artifacts', APP_ID, 'public', 'data', 'examResults', `${appUser.uid}_${activeQuiz.id}_${Date.now()}`), res);
    };

    if (activeQuiz) {
      if (finished && result) return (
        <div className="max-w-xl mx-auto bg-white p-10 rounded-3xl text-center border shadow-sm animate-in zoom-in">
          {result.passed ? <Trophy className="w-16 h-16 text-yellow-400 mx-auto mb-4"/> : <XCircle className="w-16 h-16 text-red-500 mx-auto mb-4"/>}
          <h2 className="text-2xl font-black mb-2">{result.passed ? '¡Aprobado!' : 'No aprobado'}</h2>
          {!result.passed && <p className="text-red-500 font-bold mb-6">Espera 15 minutos para volver a intentar.</p>}
          <div className="grid grid-cols-3 gap-3 mb-8"><div className="bg-gray-50 p-4 rounded-2xl"><p className="text-xs text-gray-400 font-bold uppercase">Calificación</p><p className="text-xl font-black">{result.correct}/10</p></div><div className="bg-gray-50 p-4 rounded-2xl"><p className="text-xs text-gray-400 font-bold uppercase">Puntos</p><p className="text-xl font-black">{result.totalScore}</p></div></div>
          <button onClick={()=>setActiveQuiz(null)} className="bg-gray-100 px-6 py-3 rounded-xl font-bold w-full mb-3">Volver</button>
          {result.passed && <button onClick={()=>setShowCert(true)} className="bg-[#5BC500] text-white px-6 py-3 rounded-xl font-black shadow-lg w-full flex items-center justify-center gap-2"><Award/> Ver Certificado</button>}
          {showCert && <Certificate result={result} onClose={()=>setShowCert(false)}/>}
        </div>
      );
      const q = activeQuiz.questions[currentQ];
      return (
        <div className="max-w-2xl mx-auto bg-white rounded-3xl border overflow-hidden shadow-sm">
          <div className="bg-[#019DF4] p-4 text-white flex justify-between items-center"><h3 className="font-bold">{activeQuiz.title}</h3><div className="font-mono font-bold bg-white/20 px-3 py-1 rounded-lg">{(timeLeft/60).toFixed(0)}:{(timeLeft%60).toString().padStart(2,'0')}</div></div>
          <div className="p-8"><p className="text-xl font-bold mb-6 text-[#0B2739]">{currentQ+1}. {q.q}</p><div className="space-y-3">{q.options.map((o,i)=><button key={i} onClick={()=>setAnswers({...answers,[currentQ]:i})} className={`w-full text-left p-4 rounded-2xl border-2 transition-all ${answers[currentQ]===i ? 'border-[#019DF4] bg-blue-50' : 'border-gray-100 hover:bg-gray-50'}`}>{o}</button>)}</div></div>
          <div className="p-4 bg-gray-50 border-t flex justify-between">{currentQ>0 && <button onClick={()=>setCurrentQ(c=>c-1)}>Anterior</button>}{currentQ<9 ? <button onClick={()=>setCurrentQ(c=>c+1)} disabled={answers[currentQ]===undefined} className="bg-[#019DF4] text-white px-6 py-2 rounded-xl font-bold">Siguiente</button> : <button onClick={finish} disabled={answers[currentQ]===undefined} className="bg-[#5BC500] text-white px-6 py-2 rounded-xl font-bold">Finalizar</button>}</div>
        </div>
      );
    }

    return (
      <div className="space-y-8">
        {appUser.role === 'admin' && <div className="flex bg-gray-200 p-1 rounded-xl w-64 mx-auto mb-6"><button onClick={()=>setAdminView('grid')} className={`flex-1 py-2 rounded-lg text-xs font-bold ${adminView==='grid'?'bg-white text-[#019DF4] shadow':'text-gray-500'}`}>Vista Promotor</button><button onClick={()=>setAdminView('admin')} className={`flex-1 py-2 rounded-lg text-xs font-bold ${adminView==='admin'?'bg-white text-[#019DF4] shadow':'text-gray-500'}`}>Gestión Admin</button></div>}
        {adminView === 'admin' ? (
          <div className="bg-white rounded-3xl border border-gray-100 overflow-hidden"><table className="w-full text-left text-sm"><thead className="bg-gray-50 text-gray-400 uppercase text-[10px]"><tr><th className="p-4">Promotor</th><th className="p-4">Examen</th><th className="p-4">Calificación</th><th className="p-4">Acciones</th></tr></thead><tbody>{examResults.map(r=><tr key={r.id} className="border-t"><td className="p-4 font-bold">{r.userName}</td><td className="p-4">{r.examName}</td><td className="p-4 font-black">{r.correct}/10</td><td className="p-4 flex gap-2"><button onClick={async()=>{if(window.confirm('¿Borrar?')) await deleteDoc(doc(db,'artifacts',APP_ID,'public','data','examResults',r.id));}} className="text-red-500"><Trash2 className="w-4 h-4"/></button></td></tr>)}</tbody></table></div>
        ) : (
          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">{available.map(ex => {
            const hasPassed = examResults.find(r=>r.uid===appUser.uid && r.examId===ex.id && r.passed);
            const recentFail = examResults.filter(r=>r.uid===appUser.uid && r.examId===ex.id && !r.passed).sort((a,b)=>new Date(b.timestamp)-new Date(a.timestamp))[0];
            let lockout = 0; if(recentFail && !hasPassed){ const diff = Math.floor((new Date()-new Date(recentFail.timestamp))/60000); if(diff<15) lockout=15-diff; }
            return (
              <div key={ex.id} className={`bg-white p-6 rounded-3xl border-2 transition-all ${hasPassed ? 'border-[#5BC500]/50 bg-green-50/10' : (lockout>0 ? 'border-red-100 bg-red-50/20' : 'border-gray-50 hover:border-[#019DF4]/30')}`}>
                <h4 className="text-lg font-black text-[#0B2739] mb-4">{ex.title}</h4>
                <button onClick={()=>!hasPassed && lockout===0 && start(ex)} disabled={hasPassed || lockout>0} className={`w-full py-3 rounded-2xl font-black text-sm transition-all shadow-sm ${hasPassed ? 'bg-green-100 text-green-700' : (lockout>0 ? 'bg-red-50 text-red-600' : 'bg-[#019DF4] text-white hover:shadow-md')}`}>
                   {hasPassed ? <><Check className="inline w-4 h-4 mr-2"/>Completado</> : (lockout>0 ? <><Clock className="inline w-4 h-4 mr-2"/>Bloqueado ({lockout}m)</> : 'Iniciar Evaluación')}
                </button>
              </div>
            );
          })}</div>
        )}
      </div>
    );
  };

  if (!appUser) return (
    <div className="min-h-screen bg-[#F2F4F7] flex flex-col justify-center items-center p-4">
      <div className="bg-white w-full max-w-md rounded-[40px] shadow-2xl overflow-hidden border border-gray-100">
        <div className="bg-[#019DF4] p-12 text-center text-white"><Smartphone className="w-12 h-12 mx-auto mb-4"/><h1 className="text-3xl font-black">Hidalgo Dash</h1><p className="text-blue-100 font-medium">CAPYM Academia</p></div>
        <form onSubmit={handleLogin} className="p-10 space-y-5">
           <input type="text" placeholder="Usuario" className="w-full border p-4 rounded-2xl bg-gray-50" value={loginForm.username} onChange={e=>setLoginForm({...loginForm, username: e.target.value})}/>
           <input type="password" placeholder="Contraseña" className="w-full border p-4 rounded-2xl bg-gray-50" value={loginForm.password} onChange={e=>setLoginForm({...loginForm, password: e.target.value})}/>
           {loginError && <p className="text-red-500 text-xs font-bold">{loginError}</p>}
           <button className="w-full bg-[#5BC500] text-white font-black py-4 rounded-2xl shadow-lg">Ingresar</button>
        </form>
      </div>
    </div>
  );

  return (
    <div className="min-h-screen bg-[#F2F4F7] font-sans pb-12">
      <header className="bg-[#019DF4] text-white shadow-lg border-b-4 border-[#5BC500] sticky top-0 z-40">
        <div className="max-w-7xl mx-auto px-4 py-4 flex justify-between items-center">
          <div className="flex items-center gap-2"><Smartphone/><h1 className="font-black text-xl">Hidalgo Dash</h1></div>
          <div className="flex bg-[#008CE0] p-1 rounded-xl gap-1">
             <button onClick={()=>setActiveMainTab('detalle_diario')} className={`px-4 py-1.5 rounded-lg text-xs font-black ${activeMainTab==='detalle_diario'?'bg-white text-[#019DF4]':'text-blue-100'}`}>Operación</button>
             <button onClick={()=>setActiveMainTab('academia')} className={`px-4 py-1.5 rounded-lg text-xs font-black ${activeMainTab==='academia'?'bg-white text-[#019DF4]':'text-blue-100'}`}>Academia</button>
          </div>
          <button onClick={handleLogout} className="text-blue-100 font-bold text-xs">Cerrar Sesión</button>
        </div>
      </header>
      <main className="max-w-7xl mx-auto p-4 md:p-8">
        {activeMainTab === 'academia' ? (
          <div className="space-y-8 animate-in fade-in">
             <div className="flex overflow-x-auto gap-4 border-b border-gray-200 hide-scrollbar">
                <button onClick={()=>setActiveAcademiaTab('rosters')} className={`px-6 py-4 font-black text-sm border-b-4 ${activeAcademiaTab==='rosters'?'border-[#019DF4] text-[#019DF4]':'border-transparent text-gray-400'}`}>ROSTERS</button>
                <button onClick={()=>setActiveAcademiaTab('examenes')} className={`px-6 py-4 font-black text-sm border-b-4 ${activeAcademiaTab==='examenes'?'border-[#5BC500] text-[#5BC500]':'border-transparent text-gray-400'}`}>EXÁMENES</button>
             </div>
             {activeAcademiaTab === 'rosters' ? <AcademiaRosters/> : <AcademiaExamenes/>}
          </div>
        ) : (
          <div className="animate-in fade-in">
            {appUser.role === 'admin' && (
              <div className="grid grid-cols-2 md:grid-cols-4 gap-4 mb-6"><div className="bg-white p-6 rounded-3xl shadow-sm border border-gray-100"><p className="text-xs font-bold text-gray-400">Altas</p><p className="text-3xl font-black text-[#019DF4]">{summaryOperacion.altasTotales}</p></div><div className="bg-white p-6 rounded-3xl shadow-sm border border-gray-100"><p className="text-xs font-bold text-gray-400">Alcance</p><p className="text-3xl font-black text-[#5BC500]">{summaryOperacion.alcanceTotal}%</p></div><div className="bg-white p-6 rounded-3xl shadow-sm border border-gray-100 col-span-2 flex items-center justify-between"><div className="flex flex-col gap-2"><h2 className="text-sm font-black text-[#0B2739]">Cargar Operación</h2><label className="cursor-pointer bg-[#019DF4] text-white px-4 py-2 rounded-xl text-xs font-black shadow-sm">Seleccionar Excel<input type="file" className="hidden" onChange={handleFileUploadOperacion}/></label></div>{uploadStatusOp.message && <span className="text-green-500 font-bold text-xs">{uploadStatusOp.message}</span>}</div></div>
            )}
            <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">{visibleStoresOp.map(s => <div key={s.idpdv} className="bg-white p-6 rounded-[32px] border border-gray-100 shadow-sm"><div className="flex justify-between items-start mb-4"><span className="bg-gray-100 text-gray-500 px-2 py-1 rounded-md text-[10px] font-bold font-mono">#{s.idpdv}</span><span className="bg-[#5BC500]/10 text-[#4a9e00] px-3 py-1 rounded-full text-[10px] font-black">{s.estatus}</span></div><h3 className="text-xl font-black text-[#0B2739] mb-1">{s.nombre}</h3><p className="text-xs font-bold text-gray-400 mb-4">{s.cadena}</p><div className="grid grid-cols-3 gap-2"><div className="bg-gray-50 p-3 rounded-2xl text-center"><p className="text-[10px] font-bold text-gray-400">Altas</p><p className="text-lg font-black text-[#019DF4]">{s.altas}</p></div><div className="bg-gray-50 p-3 rounded-2xl text-center"><p className="text-[10px] font-bold text-gray-400">Cuota</p><p className="text-lg font-black">{s.cuota}</p></div><div className="bg-gray-50 p-3 rounded-2xl text-center"><p className="text-[10px] font-bold text-gray-400">Alcance</p><p className="text-lg font-black text-[#5BC500]">{s.alcance}%</p></div></div></div>)}</div>
          </div>
        )}
      </main>
      <style dangerouslySetInnerHTML={{__html: `
        .hide-scrollbar::-webkit-scrollbar { display: none; }
        .hide-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
      `}} />
    </div>
  );
}

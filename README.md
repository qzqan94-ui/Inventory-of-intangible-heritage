
<html lang="ar" dir="rtl">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>استمارة حصر عنصر التراث - تفاعلية</title>
<link rel="preconnect" href="https://cdnjs.cloudflare.com" crossorigin>
<style>
/* إخفاء أي رابط داخل h1 يشير إلى هذا الرابط بالضبط */
h1 a[href="https://qzqan94-ui.github.io/jeme-vehicle/"] {
  display: none !important;
}

    :root{--bg:#f6f7fb;--card:#fff;--accent:#e8eefc;--border:#000}
    body{font-family: "Segoe UI", Tahoma, Arial, "Noto Naskh Arabic", sans-serif;background:var(--bg);padding:18px;margin:0}
    .container{max-width:950px;margin:0 auto}
    /* Results table (kept visually like original) */
    table{width:100%;border-collapse:collapse;background:var(--card);margin-bottom:18px}
    th,td{border:1px solid var(--border);padding:10px;vertical-align:top;font-size:15px}
    th.section-title{background:var(--accent);font-size:18px;text-align:right;font-weight:700;border:2px solid var(--border)}
    textarea,input[type=text],select{width:100%;border:0;font-size:15px;outline:none;resize:vertical;padding:6px}

    /* Wizard styles */
    .wizard{background:var(--card);padding:18px;border:1px solid #ddd;border-radius:6px;box-shadow:0 2px 6px rgba(0,0,0,0.04)}
    .step{display:none}
    .step.active{display:block}
    .question-title{font-weight:700;margin-bottom:8px;font-size:16px}
    .controls{display:flex;gap:8px;justify-content:space-between;margin-top:12px}
    .controls .left{display:flex;gap:8px}
    button{padding:8px 14px;border-radius:6px;border:0;background:#1f6feb;color:#fff;cursor:pointer}
    button[disabled]{opacity:0.5;cursor:not-allowed}
    .btn-ghost{background:#eee;color:#111}
    .step-counter{font-size:14px;color:#666;margin-bottom:8px}

    /* small helper */
    .small{font-size:13px;color:#444}

    /* PDF page simulation - force 5 pages when exporting */
    .pdf-pages{width:210mm;max-width:100%;margin:0 auto}
    .pdf-page{background:var(--card);padding:14mm;margin-bottom:6mm;box-shadow:0 0 0 rgba(0,0,0,0);min-height:287mm;box-sizing:border-box}
    /* Ensure page-breaks for printing */
    .page-break{page-break-after:always}

    /* hide results by default on wizard view */
    #resultsWrap{display:none}
    .topbar{display:flex;justify-content:space-between;align-items:center;margin-bottom:12px}

    /* responsive */
    @media (max-width:800px){.pdf-page{padding:12px}}
</style>
</head>
<body>
<div class="container">
  <div class="topbar">
    <h2>استمارة حصر عنصر التراث (اللحاف المصنف) — تفاعلي</h2>
    <div class="small">أجب عن كل سؤال ثم اضغط التالي — يمكنك العودة بالزر السابق</div>
  </div>

  <!-- WIZARD -->
  <div id="wizard" class="wizard" aria-live="polite">
    <div class="step-counter">سؤال <span id="currentStep">1</span> من <span id="totalSteps">24</span></div>

    <!-- Steps will be injected here -->
    <div id="stepsContainer"></div>

    <div class="controls">
      <div class="left">
        <button id="prevBtn" class="btn-ghost" type="button" disabled>السابق</button>
      </div>
      <div class="right">
        <button id="nextBtn" type="button">التالي</button>
      </div>
    </div>
  </div>

  <!-- Results (kept same structure as provided) -->
  <div id="resultsWrap">
    <div style="margin-bottom:10px;display:flex;gap:8px;justify-content:flex-end">
      <button id="backToWizard" class="btn-ghost" type="button">العودة للأسئلة</button>
      <button id="downloadPdf">تحميل PDF (5 ورقات)</button>
    </div>

    <div id="resultsArea">
      <!-- We'll render the original tables here, populated from answers -->

      <table>
          <tr><th class="section-title" colspan="2">1 ـ تحديد عنصر التراث الثقافي غير المادي</th></tr>

          <tr><th>1.1 اسم العنصر كما تستخدمه الجماعة (الاسم العامي)</th>
            <tr></tr>
              <td id="r_1_1"></td></tr>

          <tr><th>1.2 عنوان مختصر ومفيد للعنصر</th>  <tr></tr>

              <td id="r_1_2"></td></tr>

          <tr><th>1.3 الجماعة (أو الجماعات) المعنية</th><tr></tr>
              <td id="r_1_3"></td></tr>

          <tr><th>1.4 الموقع الجغرافي ونطاق الممارسة</th><tr></tr>
              <td id="r_1_4"></td></tr>

          <tr><th>1.5 وصف مختصر لعنصر التراث الثقافي غير المادي</th><tr></tr>
              <td id="r_1_5"></td></tr>

          <tr><th>1.6 مجالات التراث التي يندرج تحتها العنصر</th><tr></tr>
              <td id="r_1_6"></td></tr>

          <tr><th>1.7 الوظائف والمعاني الاجتماعية والثقافية</th><tr></tr>
              <td id="r_1_7"></td></tr>
      </table>

      <table>
        <tr><th class="section-title" colspan="2">2 ـ خصائص العنصر</th></tr>

        <tr><th>2.1 الممارسون/المؤدون</th><tr></tr>
            <td id="r_2_1"></td></tr>

        <tr><th>2.2 مشاركون آخرون</th><tr></tr>
            <td id="r_2_2"></td></tr>

        <tr><th>2.3 اللغة/اللغات المستخدمة</th><tr></tr>
            <td id="r_2_3"></td></tr>

        <tr><th>2.4 العناصر المادية المرتبطة</th><tr></tr>
            <td id="r_2_4"></td></tr>

        <tr><th>2.5 عناصر غير مادية</th><tr></tr>
            <td id="r_2_5"></td></tr>

        <tr><th>2.6 الممارسات العرفية</th><tr></tr>
            <td id="r_2_6"></td></tr>

        <tr><th>2.7 طرق النقل الحالية</th><tr></tr>
            <td id="r_2_7"></td></tr>

        <tr><th>2.8 المنظمات المعنية</th><tr></tr>
            <td id="r_2_8"></td></tr>
      </table>

      <table>
          <tr><th class="section-title" colspan="2">3 ـ حالة العنصر: قدرته على البقاء والاستدامة</th></tr>
          <tr><th>3.1 جهود الصون السابقة والحالية</th><tr></tr>
              <td id="r_3_1"></td></tr>

          <tr><th>3.2 الجهة/الجهات المختصة</th><tr></tr>
              <td id="r_3_2"></td></tr>

          <tr><th>3.3 حالة العنصر الآن</th><tr></tr>
              <td id="r_3_3"></td></tr>

          <tr><th>3.4 - 3.6 التهديدات</th><tr></tr>
              <td id="r_3_4"></td></tr>

          <tr><th>3.7 قابلية استدامة العناصر المرتبطة</th><tr></tr>
              <td id="r_3_7"></td></tr>

          <tr><th>3.8 تدابير الصون</th><tr></tr>
              <td id="r_3_8"></td></tr>
      </table>

      <table>
          <tr><th class="section-title" colspan="2">4 ـ القيود والأذونات على البيانات</th></tr>

          <tr><th>4.1 موافقة الجماعة على توفير المعلومات</th><tr></tr>
              <td id="r_4_1"></td></tr>

          <tr><th>4.2 قيود على انتفاع البيانات</th><tr></tr>
              <td id="r_4_2"></td></tr>

          <tr><th>4.3 الأشخاص المخبرون</th><tr></tr>
              <td id="r_4_3"></td></tr>

          <tr><th>4.4 تواريخ جمع المعلومات</th><tr></tr>
              <td id="r_4_4"></td></tr>
      </table>

      <table>
          <tr><th class="section-title" colspan="2">5 ـ المراجع</th></tr>
          <tr><th>5.1 الأدبيات</th><tr></tr>
              <td id="r_5_1"></td></tr>
          <tr><th>5.2 مواد سمعية وبصرية</th><tr></tr>
              <td id="r_5_2"></td></tr>

          <tr><th>5.3 مواد وثائقية وأدوات في المتاحف</th><tr></tr>
              <td id="r_5_3"></td></tr>
      </table>

    </div>

    <!-- PDF pages container (hidden in UI but used when generating PDF) -->
    <div id="pdfPagesContainer" style="display:none"></div>
  </div>

</div>

<!-- include html2pdf from CDN -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.9.3/html2pdf.bundle.min.js"></script>
<script>
// Definition of fields/questions in order (one page = one question view)
const questions = [
  {id:'q_1_1',label:'1.1 اسم العنصر كما تستخدمه الجماعة (الاسم العامي)',type:'text',placeholder:''},
  {id:'q_1_2',label:'1.2 عنوان مختصر ومفيد للعنصر',type:'text'},
  {id:'q_1_3',label:'1.3 الجماعة (أو الجماعات) المعنية',type:'text'},
  {id:'q_1_4',label:'1.4 الموقع الجغرافي ونطاق الممارسة',type:'text'},
  {id:'q_1_5',label:'1.5 وصف مختصر لعنصر التراث الثقافي غير المادي',type:'textarea'},
  {id:'q_1_6',label:'1.6 مجالات التراث التي يندرج تحتها العنصر (اكتب/اختر)',type:'textarea',placeholder:'مثال: الفنون الأدائية، التعابير الشفهية...'},
  {id:'q_1_7',label:'1.7 الوظائف والمعاني الاجتماعية والثقافية',type:'textarea'},

  {id:'q_2_1',label:'2.1 الممارسون/المؤدون (الاسم، العمر، الجنس، تواصل)',type:'textarea',value:
`الاسم:
العمر:
الجنس:
التواصل:`},
  {id:'q_2_2',label:'2.2 مشاركون آخرون',type:'textarea',value:
`الاسم:
العمر:
الجنس:
التواصل:`},
  {id:'q_2_3',label:'2.3 اللغة/اللغات المستخدمة',type:'text',value:'اللغة العربية'},
  {id:'q_2_4',label:'2.4 العناصر المادية المرتبطة',type:'textarea'},
  {id:'q_2_5',label:'2.5 عناصر غير مادية',type:'textarea'},
  {id:'q_2_6',label:'2.6 الممارسات العرفية',type:'textarea'},
  {id:'q_2_7',label:'2.7 طرق النقل الحالية',type:'text'},
  {id:'q_2_8',label:'2.8 المنظمات المعنية',type:'textarea'},


{
  id:'q_3_1',
  label:'3.1 جهود الصون السابقة والحالية',
type:'textarea',value:
  `النقل (التعليم الرسمي والغير رسمي).
التوثيق والبحث.
الحفظ والحماية.
الترويج والتعزيز.`
},

  {id:'q_3_2',label:'3.2 الجهة/الجهات المختصة',type:'text'},
  {id:'q_3_3',label:'3.3 حالة العنصر الآن',type:'select',options:['مازال محافظًا عليه','بحاجة لصون','يتلاشى']},
  {id:'q_3_4',label:'3.4 - 3.6 التهديدات',type:'textarea'},
  {id:'q_3_7',label:'3.7 قابلية استدامة العناصر المرتبطة',type:'text'},
  {id:'q_3_8',label:'3.8 تدابير الصون',type:'textarea'},

  {id:'q_4_1',label:'4.1 موافقة الجماعة على توفير المعلومات',type:'text'},
  {id:'q_4_2',label:'4.2 قيود على انتفاع البيانات',type:'text'},
  {id:'q_4_3',label:'4.3 الأشخاص المخبرون (الاسم، المكانة، الانتماء)',type:'textarea',value:`الاسم:
العمر:
الجنس:
التواصل:`},
  {id:'q_4_4',label:'4.4 تواريخ جمع المعلومات',type:'text'},

  {id:'q_5_1',label:'5.1 الأدبيات',type:'textarea'},
  {id:'q_5_2',label:'5.2 مواد سمعية وبصرية',type:'text'},
  {id:'q_5_3',label:'5.3 مواد وثائقية وأدوات في المتاحف',type:'text'}
];

const totalSteps = questions.length;
document.getElementById('totalSteps').textContent = totalSteps;

// Render steps
const stepsContainer = document.getElementById('stepsContainer');
questions.forEach((q, idx)=>{
  const step = document.createElement('div');
  step.className = 'step';
  step.id = 'step_'+idx;

  const title = document.createElement('div');
  title.className = 'question-title';
  title.textContent = q.label;
  step.appendChild(title);

  let input;
  if(q.type==='textarea'){
    input = document.createElement('textarea');
    input.rows = 6;
  } else if(q.type==='select'){
    input = document.createElement('select');
    q.options.forEach(opt=>{const o=document.createElement('option');o.value=opt;o.textContent=opt;input.appendChild(o)});
  } else {
    input = document.createElement('input');
    input.type = 'text';
  }
  input.id = q.id;
  input.setAttribute('aria-label', q.label);
  if(q.value) input.value = q.value;
  step.appendChild(input);

  // helper text
  const helper = document.createElement('div');
  helper.className='small';
  helper.textContent='أدخل الإجابة ثم اضغط التالي. يمكنك الرجوع بالضغط على السابق.';
  step.appendChild(helper);

  stepsContainer.appendChild(step);
});

// show first step
let current = 0;
function showStep(n){
  document.querySelectorAll('.step').forEach((el,i)=>{
    el.classList.toggle('active', i===n);
  });
  document.getElementById('currentStep').textContent = n+1;
  document.getElementById('prevBtn').disabled = n===0;
  const nextBtn = document.getElementById('nextBtn');
  nextBtn.textContent = (n===totalSteps-1)?'إنهاء وعرض النتائج':'التالي';
}
showStep(current);

// Navigation
document.getElementById('nextBtn').addEventListener('click', ()=>{
  // simple validation: required non-empty for current
  const curQ = questions[current];
  const input = document.getElementById(curQ.id);
  const val = (input.value||'').trim();
  if(!val){
    // allow empty for non-critical? we'll require at least something
    alert('الرجاء إدخال إجابة للسؤال قبل المتابعة.');
    input.focus();
    return;
  }

  if(current < totalSteps-1){
    current++;
    showStep(current);
    window.scrollTo(0,0);
  } else {
    // finish -> populate results
    populateResults();
    document.getElementById('wizard').style.display='none';
    document.getElementById('resultsWrap').style.display='block';
    window.scrollTo(0,0);
  }
});

document.getElementById('prevBtn').addEventListener('click', ()=>{
  if(current>0){current--;showStep(current);window.scrollTo(0,0)}
});

document.getElementById('backToWizard').addEventListener('click', ()=>{
  document.getElementById('resultsWrap').style.display='none';
  document.getElementById('wizard').style.display='block';
  // go to last question
  current = 0; showStep(current); window.scrollTo(0,0);
});

// Populate results into table
function populateResults(){
  // mapping from question id to result element id
  const map = {
    'q_1_1':'r_1_1','q_1_2':'r_1_2','q_1_3':'r_1_3','q_1_4':'r_1_4','q_1_5':'r_1_5','q_1_6':'r_1_6','q_1_7':'r_1_7',
    'q_2_1':'r_2_1','q_2_2':'r_2_2','q_2_3':'r_2_3','q_2_4':'r_2_4','q_2_5':'r_2_5','q_2_6':'r_2_6','q_2_7':'r_2_7','q_2_8':'r_2_8',
    'q_3_1':'r_3_1','q_3_2':'r_3_2','q_3_3':'r_3_3','q_3_4':'r_3_4','q_3_7':'r_3_7','q_3_8':'r_3_8',
    'q_4_1':'r_4_1','q_4_2':'r_4_2','q_4_3':'r_4_3','q_4_4':'r_4_4',
    'q_5_1':'r_5_1','q_5_2':'r_5_2','q_5_3':'r_5_3'
  };
  for(const q of questions){
  const val = (document.getElementById(q.id).value || '')
                .replace(/\n/g, '<br>');
  const rid = map[q.id];
  if(rid) document.getElementById(rid).innerHTML = val;
}


  // Prepare PDF pages (5 pages) by splitting sections logically
  const pages = [];
  // page 1: section 1
  pages.push(document.querySelector('table:nth-of-type(1)').outerHTML);
  // page 2: section 2
  pages.push(document.querySelector('table:nth-of-type(2)').outerHTML);
  // page 3: section 3
  pages.push(document.querySelector('table:nth-of-type(3)').outerHTML);
  // page 4: section 4
  pages.push(document.querySelector('table:nth-of-type(4)').outerHTML);
  // page 5: section 5
  pages.push(document.querySelector('table:nth-of-type(5)').outerHTML);

  // build pdf pages container hidden
  const pdfContainer = document.getElementById('pdfPagesContainer');
  pdfContainer.innerHTML = '';
  pages.forEach((html, i)=>{
    const page = document.createElement('div');
    page.className = 'pdf-page';
    page.innerHTML = html;
    pdfContainer.appendChild(page);
    if(i < pages.length-1){ const br=document.createElement('div'); br.className='page-break'; pdfContainer.appendChild(br);} 
  });
}

document.getElementById('downloadPdf').addEventListener('click', ()=>{
  const pdfContainer = document.getElementById('pdfPagesContainer');
  
  if(!pdfContainer.innerHTML.trim()){
    alert('يرجى أولًا إنهاء الإجابة على الأسئلة لعرض النتائج ثم تحميل PDF.');
    return;
  }

  const opt = {
    margin:       [0,0,0,0],
    filename:     'استمارة_حصر_عنصر_التراث.pdf',
    image:        { type: 'jpeg', quality: 1 },
    html2canvas:  { scale: 3, useCORS: true, letterRendering: true },
    jsPDF:        { unit: 'mm', format: 'a4', orientation: 'portrait' }
  };

  pdfContainer.style.display = 'block';

// نسخ العنصر
const clone = pdfContainer.cloneNode(true);
clone.style.width = '210mm';
clone.style.minHeight = '297mm';
clone.style.boxSizing = 'border-box';

// **نسخ القيم التفاعلية إلى نصوص ثابتة**
clone.querySelectorAll('input, textarea, select').forEach(el => {
  const value = el.value;
  const span = document.createElement('span');
  span.textContent = value;
  el.parentNode.replaceChild(span, el);
});

// تغليف العنصر
const wrapper = document.createElement('div');
wrapper.style.width = '210mm';
wrapper.appendChild(clone);

// توليد PDF
html2pdf()
  .set(opt)
  .from(wrapper)
  .toPdf()
  .get('pdf')
  .then((pdf) => {
      const totalPages = pdf.internal.getNumberOfPages();
      
      // حذف الصفحات بعد الصفحة الخامسة
      for(let i = totalPages; i > 5; i--){
          pdf.deletePage(i);
      }
  })
  .save()
  .then(()=>{
      pdfContainer.style.display = 'none';
  })
  .catch(err=>{
      console.error(err);
      alert('حدث خطأ أثناء إنشاء ملف PDF.');
  });


});


// initialize by focusing first input
setTimeout(()=>{ const firstInput=document.getElementById(questions[0].id); if(firstInput) firstInput.focus(); },300);
</script>
</body>
</html>

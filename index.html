  all.unshift(booking);
  localStorage.setItem(STORAGE_KEY, JSON.stringify(all));
}

function isSupabaseConfigured(){
  return SUPABASE_CONFIG.url !== 'YOUR_SUPABASE_URL' && SUPABASE_CONFIG.anonKey !== 'YOUR_SUPABASE_ANON_KEY';
}

function getSupabaseClient(){
  if(!isSupabaseConfigured()) return null;
  if(!supabase){
    supabase = createClient(SUPABASE_CONFIG.url, SUPABASE_CONFIG.anonKey);
  }
  return supabase;
}

function setStatus(message, type=''){
  formStatus.textContent = message;
  formStatus.className = 'form-status' + (type ? ' ' + type : '');
}

function resetStatus(){
  setStatus('');
}

document.querySelectorAll('.event-card').forEach(card=>{
  card.addEventListener('click',()=>{
    document.querySelectorAll('.event-card').forEach(c=>c.classList.remove('selected'));
    card.classList.add('selected');
    selectedEvent = card.dataset.val;
    resetStatus();
  });
});

window.goStep = function goStep(n){
  if(n===2 && !selectedEvent){
    alert('Please choose an event type first.');
    return;
  }
  document.querySelectorAll('.step-panel').forEach(p=>p.classList.remove('active'));
  document.getElementById('step'+n).classList.add('active');
  for(let i=1;i<=3;i++){
    const pip=document.getElementById('pip'+i);
    pip.classList.remove('active','done');
    if(i===n) pip.classList.add('active');
    if(i<n) pip.classList.add('done');
  }
  resetStatus();
  document.getElementById('booking').scrollIntoView({behavior:'smooth',block:'start'});
};

function collectBooking(){
  return {
    submitted_at: new Date().toISOString(),
    event_type: selectedEvent,
    first_name: document.getElementById('fname').value.trim(),
    last_name: document.getElementById('lname').value.trim(),
    email: document.getElementById('email').value.trim(),
    phone: document.getElementById('phone').value.trim(),
    event_date: document.getElementById('edate').value || null,
    guest_count: document.getElementById('guests').value ? Number(document.getElementById('guests').value) : null,
    city: document.getElementById('city').value,
    vibe: document.getElementById('vibe').value,
    budget: document.getElementById('budget').value,
    notes: document.getElementById('notes').value.trim()
  };
}

function validateBooking(booking){
  if(!booking.event_type) return { ok:false, message:'Please choose an event type first.', step:1 };
  if(!booking.first_name || !booking.email) return { ok:false, message:'Please fill in at least your first name and email.', step:2 };
  return { ok:true };
}

async function saveBookingToSupabase(booking){
  const client = getSupabaseClient();
  if(!client) return { saved:false, mode:'local-only' };

  const payload = {
    ...booking,
    status: 'new',
    source: 'website'
  };

  const { error } = await client.from(SUPABASE_CONFIG.table).insert(payload);
  if(error) throw error;
  return { saved:true, mode:'supabase' };
}

window.submitBooking = async function submitBooking(){
  const booking = collectBooking();
  const validation = validateBooking(booking);

  if(!validation.ok){
    setStatus(validation.message, 'error');
    goStep(validation.step);
    return;
  }

  submitBtn.disabled = true;
  setStatus('Sending your request...', '');

  const localBackup = {
    id: Date.now(),
    ...booking,
    submitted: new Date().toLocaleString()
  };

  try{
    saveBookingLocal(localBackup);
    const result = await saveBookingToSupabase(booking);
    setStatus(
      result.mode === 'supabase'
        ? 'Request sent successfully.'
        : 'Saved locally for now. Add your Supabase keys to start collecting live submissions.',
      'success'
    );
    showConfirm();
  }catch(error){
    console.error('Booking submission failed:', error);
    setStatus('Your request was saved locally, but the live database connection needs attention.', 'error');
    showConfirm();
  }finally{
    submitBtn.disabled = false;
  }
};

function showConfirm(){
  const el=document.getElementById('confirm');
  el.classList.add('show');
  document.body.style.overflow='hidden';
  spawnParticles();
}

window.closeConfirm = function closeConfirm(){
  document.getElementById('confirm').classList.remove('show');
  document.body.style.overflow='';
  goStep(1);
  selectedEvent='';
  resetStatus();
  document.querySelectorAll('.event-card').forEach(c=>c.classList.remove('selected'));
  document.querySelectorAll('input,textarea').forEach(i=>i.value='');
  document.querySelectorAll('select').forEach(s=>s.selectedIndex=0);
};

function spawnParticles(){
  const el=document.getElementById('confirm');
  for(let i=0;i<20;i++){
    const p=document.createElement('div');
    p.classList.add('particle');
    const size=Math.random()*6+3;
    p.style.cssText=`width:${size}px;height:${size}px;left:${Math.random()*100}%;bottom:0;animation-duration:${Math.random()*3+2.5}s;animation-delay:${Math.random()*2}s;background:${Math.random()>.5?'var(--red)':'var(--amber)'};`;
    el.appendChild(p);
    setTimeout(()=>p.remove(),6000);
  }
}

const io=new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){
      e.target.classList.add('on');
      io.unobserve(e.target);
    }
  });
},{threshold:.1});

document.querySelectorAll('.reveal').forEach(el=>io.observe(el));

window.viewBookings=function(){
  const b=getBookings();
  if(!b.length){
    console.log('No bookings yet.');
    return;
  }
  console.table(b);
  console.log('\nFull data:\n',JSON.stringify(b,null,2));
};

window.supabaseSetupHelp = function supabaseSetupHelp(){
  console.log(`1. Create a table named "${SUPABASE_CONFIG.table}" in Supabase.
2. Add columns that match the booking payload fields:
   submitted_at, event_type, first_name, last_name, email, phone,
   event_date, guest_count, city, vibe, budget, notes, status, source
3. Replace SUPABASE_CONFIG.url and SUPABASE_CONFIG.anonKey in this file.
4. Enable an insert policy for anonymous users if you're using Row Level Security.`);
};
</script>
</body>
</html>

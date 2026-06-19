// ===== Nav scroll state =====
const nav = document.querySelector('.site-nav');
function onScroll(){
  if(window.scrollY > 40){ nav.classList.add('scrolled'); }
  else{ nav.classList.remove('scrolled'); }
}
window.addEventListener('scroll', onScroll);
onScroll();

// ===== Mobile nav toggle =====
const toggle = document.querySelector('.nav-toggle');
const links = document.querySelector('.nav-links');
if(toggle && links){
  toggle.addEventListener('click', () => {
    toggle.classList.toggle('open');
    links.classList.toggle('open');
  });
  links.querySelectorAll('a').forEach(a => {
    a.addEventListener('click', () => {
      toggle.classList.remove('open');
      links.classList.remove('open');
    });
  });
}

// ===== Reveal on scroll =====
const revealEls = document.querySelectorAll('.reveal');
const io = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if(entry.isIntersecting){
      entry.target.classList.add('visible');
      io.unobserve(entry.target);
    }
  });
}, { threshold: 0.15 });
revealEls.forEach(el => io.observe(el));

// ===== Menu tabs (menu page only) =====
const tabs = document.querySelectorAll('.menu-tab');
const menuSections = document.querySelectorAll('.menu-section');
tabs.forEach(tab => {
  tab.addEventListener('click', () => {
    const target = tab.dataset.target;
    tabs.forEach(t => t.classList.remove('active'));
    menuSections.forEach(s => s.classList.remove('active'));
    tab.classList.add('active');
    document.getElementById(target).classList.add('active');
  });
});

// ===== Contact form (demo only) =====
const form = document.querySelector('.form');
if(form){
  form.addEventListener('submit', (e) => {
    e.preventDefault();
    const btn = form.querySelector('button[type="submit"]');
    const original = btn.textContent;
    btn.textContent = 'Request sent';
    btn.disabled = true;
    setTimeout(() => {
      btn.textContent = original;
      btn.disabled = false;
      form.reset();
    }, 2400);
  });
}

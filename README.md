<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Premium Outlet — Shop</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&family=Playfair+Display:wght@600&display=swap" rel="stylesheet">
  <style>
    /* ---------- Reset & base ---------- */
    :root{
      --bg:#0f1724; /* deep navy */
      --card:#0b1320;
      --muted:#95a0b8;
      --accent1:#ff6b6b; /* coral */
      --accent2:#7c5cff; /* violet */
      --glass: rgba(255,255,255,0.06);
      --glass-strong: rgba(255,255,255,0.08);
      --gold: #ffd166;
      --radius:16px;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family:Inter,system-ui,Arial, sans-serif;
      background:linear-gradient(180deg,#081021 0%, #071427 40% , #051226 100%);
      color:#e6eef8;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      padding:28px;
    }

    /* ---------- Layout ---------- */
    .wrap{max-width:1200px;margin:0 auto;display:grid;grid-template-columns:1fr 360px;gap:24px;align-items:start}
    header{display:flex;justify-content:space-between;align-items:center;margin-bottom:18px}
    .brand{display:flex;gap:12px;align-items:center}
    .logo{background:linear-gradient(90deg,var(--accent2),var(--accent1));padding:10px;border-radius:12px;box-shadow:0 4px 30px rgba(124,92,255,0.14);}
    .logo h1{font-family: 'Playfair Display', serif;margin:0;font-size:18px;letter-spacing:0.3px}
    .searchBox{display:flex;gap:12px;align-items:center}
    .searchBox input{background:var(--glass);border:0;padding:10px 14px;border-radius:12px;color:inherit;min-width:260px}
    .controls{display:flex;gap:8px;align-items:center}
    .btn{background:var(--glass);border:1px solid rgba(255,255,255,0.04);padding:10px 12px;border-radius:12px;cursor:pointer}

    /* ---------- Products ---------- */
    .catalog{background:linear-gradient(180deg, rgba(255,255,255,0.02), transparent);padding:20px;border-radius:var(--radius);box-shadow:0 6px 30px rgba(2,6,23,0.6)}
    .filters{display:flex;gap:12px;align-items:center;margin-bottom:14px}
    .filters select{background:transparent;border:1px solid rgba(255,255,255,0.04);padding:8px 10px;border-radius:10px;color:inherit}
    .grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));gap:18px}

    .card{background:linear-gradient(180deg,var(--card), #071226);padding:12px;border-radius:14px;border:1px solid rgba(255,255,255,0.03);position:relative;overflow:hidden}
    .media{height:180px;border-radius:10px;display:flex;align-items:center;justify-content:center;background:linear-gradient(135deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));margin-bottom:12px}
    .media img{max-width:92%;max-height:92%;object-fit:contain}
    .badge{position:absolute;left:12px;top:12px;padding:6px 8px;border-radius:10px;font-size:12px;font-weight:600}
    .badge.new{background:linear-gradient(90deg,var(--accent2),var(--accent1));color:#fff}
    .badge.sale{background:var(--gold);color:#081022}

    .title{font-weight:600;margin:0 0 6px 0}
    .meta{color:var(--muted);font-size:13px;margin-bottom:8px}
    .priceRow{display:flex;justify-content:space-between;align-items:center}
    .price{font-weight:700}
    .old{color:var(--muted);text-decoration:line-through;font-size:12px;margin-left:8px}

    .actions{display:flex;gap:8px;margin-top:10px}
    .iconBtn{background:transparent;border:1px solid rgba(255,255,255,0.04);padding:8px;border-radius:10px;cursor:pointer}
    .addBtn{flex:1;background:linear-gradient(90deg,var(--accent1),var(--accent2));color:#051024;border:0;padding:10px;border-radius:10px;font-weight:700;cursor:pointer}

    /* ---------- Cart ---------- */
    .cartPane{position:sticky;top:28px;background:linear-gradient(180deg,#061022 0%, #041022 100%);padding:16px;border-radius:16px;border:1px solid rgba(255,255,255,0.03)}
    .cartHeader{display:flex;justify-content:space-between;align-items:center;margin-bottom:12px}
    .cartItems{max-height:420px;overflow:auto;padding-right:6px}
    .cartItem{display:flex;gap:12px;align-items:center;padding:10px 0;border-bottom:1px dashed rgba(255,255,255,0.02)}
    .cartItem img{width:56px;height:56px;border-radius:8px;object-fit:cover}
    .qty{display:flex;gap:6px;align-items:center}
    .checkout{background:linear-gradient(90deg,var(--accent2),var(--accent1));border:0;padding:12px;border-radius:12px;width:100%;font-weight:800;cursor:pointer;margin-top:12px}

    /* ---------- Modal ---------- */
    .modal{position:fixed;inset:0;display:flex;align-items:center;justify-content:center;background:rgba(2,6,23,0.6);backdrop-filter:blur(6px);visibility:hidden;opacity:0;transition:all .18s}
    .modal.show{visibility:visible;opacity:1}
    .modalCard{background:linear-gradient(180deg,#071226,#06102a);padding:18px;border-radius:14px;max-width:880px;width:94%;display:grid;grid-template-columns:1fr 1fr;gap:18px}

    /* ---------- Footer ---------- */
    footer{margin-top:20px;color:var(--muted);text-align:center}

    /* ---------- Responsive ---------- */
    @media (max-width:980px){.wrap{grid-template-columns:1fr;}.cartPane{position:static}} 

    /* subtle micro animations */
    .card:hover{transform:translateY(-6px);transition:transform .18s}
    .addBtn:active{transform:scale(.98)}
  </style>
</head>
<body>
  <header>
    <div class="brand">
      <div class="logo"><h1>Premium Outlet</h1></div>
      <div>
        <div style="font-weight:700">Premium Outlet</div>
        <div style="font-size:12px;color:var(--muted)">Curated luxury, everyday prices</div>
      </div>
    </div>

    <div class="searchBox">
      <input id="search" placeholder="Search products, e.g. 'sneakers'" />
      <div class="controls">
        <button class="btn" id="openCartBtn">Cart (<span id="cartCount">0</span>)</button>
      </div>
    </div>
  </header>

  <main class="wrap">
    <section class="catalog">
      <div class="filters">
        <select id="categoryFilter"><option value="all">All Categories</option></select>
        <select id="sortBy"><option value="popular">Sort: Popular</option><option value="price-asc">Price low → high</option><option value="price-desc">Price high → low</option></select>
        <div style="margin-left:auto;color:var(--muted);font-size:13px">Showing <span id="resultCount">0</span> products</div>
      </div>

      <div class="grid" id="productGrid"></div>
    </section>

    <aside class="cartPane">
      <div class="cartHeader">
        <div style="font-weight:800">Your Cart</div>
        <div style="color:var(--muted);font-size:13px" id="cartSubtotalText">₹0.00</div>
      </div>
      <div class="cartItems" id="cartItems"></div>
      <button class="checkout" id="checkoutBtn">Checkout — Pay ₹<span id="cartTotal">0</span></button>
      <div style="margin-top:10px;color:var(--muted);font-size:13px">Secure checkout • 30‑day returns</div>
    </aside>
  </main>

  <footer>
    © <span id="year"></span> Premium Outlet — Crafted with care
  </footer>

  <!-- Quick view modal -->
  <div class="modal" id="modal">
    <div class="modalCard">
      <div style="display:flex;align-items:center;justify-content:center;background:linear-gradient(180deg, #071226, #051124);border-radius:8px;padding:18px">
        <img id="modalImg" src="" style="max-width:100%;max-height:320px;object-fit:contain" />
      </div>
      <div>
        <div style="display:flex;justify-content:space-between;align-items:center">
          <div>
            <h2 id="modalTitle" style="margin:0"></h2>
            <div id="modalBadge" style="font-size:13px;color:var(--muted)"></div>
          </div>
          <div><button class="btn" id="modalClose">Close</button></div>
        </div>
        <p id="modalDesc" style="color:var(--muted)"></p>
        <div style="margin-top:10px;font-weight:800;font-size:18px">₹<span id="modalPrice"></span> <span id="modalOld" style="text-decoration:line-through;color:var(--muted);font-weight:400;margin-left:8px"></span></div>
        <div style="margin-top:12px;display:flex;gap:8px">
          <button class="addBtn" id="modalAdd">Add to cart</button>
          <button class="btn" id="modalFav">❤ Wishlist</button>
        </div>
      </div>
    </div>
  </div>

  <script>
    // ----------------- Sample product data -----------------
    const sampleProducts = [
      {id:1, title:'Aurora Running Sneakers', category:'Footwear', price:3499, oldPrice:4999, img:'https://images.unsplash.com/photo-1600180758890-22b7d2a3f8a0?q=80&w=800&auto=format&fit=crop&ixlib=rb-4.0.3&s=1', badge:'new', rating:4.7, desc:'Cushioned sneakers with breathable knit upper.'},
      {id:2, title:'Luxe Leather Wallet', category:'Accessories', price:1299, oldPrice:null, img:'https://images.unsplash.com/photo-1522441815190-60f0a8a4d5a2?q=80&w=800&auto=format&fit=crop&ixlib=rb-4.0.3&s=2', badge:null, rating:4.3, desc:'Hand-stitched leather wallet with RFID protection.'},
      {id:3, title:'Nebula Smartwatch', category:'Wearables', price:8999, oldPrice:10999, img:'https://images.unsplash.com/photo-1523275335684-37898b6baf30?q=80&w=800&auto=format&fit=crop&ixlib=rb-4.0.3&s=3', badge:'sale', rating:4.5, desc:'All-day battery with health tracking and AMOLED display.'},
      {id:4, title:'Cobalt Knit Sweater', category:'Apparel', price:2199, oldPrice:2799, img:'https://images.unsplash.com/photo-1541099649105-f69ad21f3246?q=80&w=800&auto=format&fit=crop&ixlib=rb-4.0.3&s=4', badge:'new', rating:4.2, desc:'Soft merino blend sweater, slim fit.'},
      {id:5, title:'Auric Headphones', category:'Audio', price:5499, oldPrice:6999, img:'https://images.unsplash.com/photo-1518444029130-6e1d34ad7c17?q=80&w=800&auto=format&fit=crop&ixlib=rb-4.0.3&s=5', badge:null, rating:4.6, desc:'Noise-cancelling over-ear headphones with rich bass.'},
      {id:6, title:'Solstice Sunglasses', category:'Accessories', price:1499, oldPrice:1999, img:'https://images.unsplash.com/photo-1503342452485-86f7f6f3b0a3?q=80&w=800&auto=format&fit=crop&ixlib=rb-4.0.3&s=6', badge:null, rating:4.1, desc:'Polarized lenses with UV protection.'}
    ];

    // ----------------- State & helpers -----------------
    let products = sampleProducts.slice();
    let cart = JSON.parse(localStorage.getItem('po_cart') || '{}');

    const el = id => document.getElementById(id);
    const productGrid = el('productGrid');
    const categoryFilter = el('categoryFilter');
    const sortBy = el('sortBy');
    const search = el('search');
    const resultCount = el('resultCount');
    const cartItemsEl = el('cartItems');
    const cartCount = el('cartCount');
    const cartTotal = el('cartTotal');
    const cartSubtotalText = el('cartSubtotalText');
    const year = el('year');
    year.textContent = new Date().getFullYear();

    // build categories
    const categories = Array.from(new Set(products.map(p=>p.category)));
    categories.forEach(c=>{ const opt=document.createElement('option');opt.value=c;opt.textContent=c;categoryFilter.appendChild(opt)});

    // render product grid
    function renderProducts(list){
      productGrid.innerHTML='';
      list.forEach(p=>{
        const card = document.createElement('div');card.className='card';
        card.innerHTML = `
          <div class='badge ${p.badge? (p.badge==='sale'?'sale':'new') : ''}'>${p.badge? p.badge.toUpperCase(): ''}</div>
          <div class='media'><img src='${p.img}' alt='${p.title}' loading='lazy'/></div>
          <div>
            <h3 class='title'>${p.title}</h3>
            <div class='meta'>${p.category} • ⭐ ${p.rating}</div>
            <div class='priceRow'><div class='price'>₹${p.price}</div>${p.oldPrice?`<div class='old'>₹${p.oldPrice}</div>`: ''}</div>
            <div class='actions'>
              <button class='iconBtn' data-action='view' data-id='${p.id}'>Quick view</button>
              <button class='addBtn' data-action='add' data-id='${p.id}'>Add to cart</button>
            </div>
          </div>
        `;
        productGrid.appendChild(card);
      });
      resultCount.textContent = list.length;
    }

    // filter / sort / search
    function applyFilters(){
      let list = products.slice();
      const cat = categoryFilter.value;
      const q = search.value.trim().toLowerCase();
      if(cat!=='all') list = list.filter(p=>p.category===cat);
      if(q) list = list.filter(p=> (p.title+ ' ' + p.desc + ' ' + p.category).toLowerCase().includes(q));
      const s = sortBy.value;
      if(s==='price-asc') list.sort((a,b)=>a.price-b.price);
      if(s==='price-desc') list.sort((a,b)=>b.price-a.price);
      renderProducts(list);
    }

    // cart helpers
    function saveCart(){ localStorage.setItem('po_cart', JSON.stringify(cart)); renderCart(); }
    function addToCart(id, qty=1){ cart[id] = (cart[id]||0) + qty; saveCart(); }
    function removeFromCart(id){ delete cart[id]; saveCart(); }
    function setQty(id, q){ if(q<=0) removeFromCart(id); else { cart[id]=q; saveCart(); } }

    function renderCart(){
      cartItemsEl.innerHTML='';
      let subtotal=0, count=0;
      Object.keys(cart).forEach(id=>{
        const p = products.find(x=>x.id==id); if(!p) return;
        const q = cart[id]; count += q; subtotal += p.price * q;
        const node = document.createElement('div'); node.className='cartItem';
        node.innerHTML = `
          <img src='${p.img}' alt='${p.title}' />
          <div style='flex:1'>
            <div style='font-weight:700'>${p.title}</div>
            <div style='color:var(--muted);font-size:13px'>₹${p.price} • ${p.category}</div>
          </div>
          <div class='qty'>
            <button class='btn' data-action='minus' data-id='${id}'>-</button>
            <div style='min-width:20px;text-align:center'>${q}</div>
            <button class='btn' data-action='plus' data-id='${id}'>+</button>
          </div>
        `;
        cartItemsEl.appendChild(node);
      });
      cartCount.textContent = count;
      cartTotal.textContent = subtotal.toFixed(0);
      cartSubtotalText.textContent = `₹${subtotal.toFixed(0)}`;
    }

    // product quick view
    const modal = el('modal');
    function showModalFor(id){
      const p = products.find(x=>x.id==id); if(!p) return;
      el('modalImg').src = p.img;
      el('modalTitle').textContent = p.title;
      el('modalDesc').textContent = p.desc;
      el('modalPrice').textContent = p.price;
      el('modalOld').textContent = p.oldPrice? '₹'+p.oldPrice : '';
      el('modalBadge').textContent = p.badge? p.badge.toUpperCase() : '';
      el('modal').classList.add('show');
      el('modalAdd').dataset.id = id;
    }

    // ---------- Events ----------
    document.addEventListener('click', e=>{
      const a = e.target.dataset.action;
      const id = e.target.dataset.id;
      if(a==='add') addToCart(id,1);
      if(a==='view') showModalFor(id);
      if(a==='plus') setQty(id, (cart[id]||0)+1);
      if(a==='minus') setQty(id, (cart[id]||0)-1);
    });

    el('modalClose').addEventListener('click', ()=> modal.classList.remove('show'));
    el('modal').addEventListener('click', ev=>{ if(ev.target===modal) modal.classList.remove('show'); });
    el('modalAdd').addEventListener('click', ()=>{ addToCart(el('modalAdd').dataset.id,1); modal.classList.remove('show'); });

    categoryFilter.addEventListener('change', applyFilters);
    sortBy.addEventListener('change', applyFilters);
    search.addEventListener('input', (()=>{ let t; return function(){ clearTimeout(t); t=setTimeout(applyFilters,200) } })());

    el('checkoutBtn').addEventListener('click', ()=>{
      if(Object.keys(cart).length===0) return alert('Your cart is empty. Add items to checkout.');
      // simple demo checkout flow (not real payments)
      localStorage.removeItem('po_cart'); cart={}; saveCart(); alert('Thanks! Your order has been placed (demo).');
    });

    el('openCartBtn').addEventListener('click', ()=>{
      window.scrollTo({top:document.body.scrollHeight, behavior:'smooth'});
    });

    // init
    renderProducts(products);
    renderCart();
  </script>
</body>
</html>
# ecom-website

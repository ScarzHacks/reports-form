// Tailwind script already loaded in HTML

let reports = [];

// Load or create sample data
function initReports() {
  const saved = localStorage.getItem('kylitoReports');
  if (saved) {
    reports = JSON.parse(saved);
  } else {
    // Sample reports so you can test immediately
    reports = [
      {
        id: "1",
        username: "ToxicPlayer#6969",
        reason: "harassment",
        details: "Kept spamming slurs in voice chat and targeted me after losing a match.",
        anonymous: false,
        evidence: ["chat-log.png", "voice-clip.mp4"],
        timestamp: "2026-02-27T22:15:00.000Z"
      },
      {
        id: "2",
        username: "spamBot123",
        reason: "spam",
        details: "Sending referral links in every channel for the last 3 days.",
        anonymous: true,
        evidence: ["screenshot1.jpg"],
        timestamp: "2026-02-28T10:30:00.000Z"
      },
      {
        id: "3",
        username: "cheaterX",
        reason: "cheating",
        details: "Using aimbot and speed hacks in ranked matches - obvious from replay.",
        anonymous: false,
        evidence: [],
        timestamp: "2026-02-28T14:05:00.000Z"
      }
    ];
    localStorage.setItem('kylitoReports', JSON.stringify(reports));
  }
  renderReports();
}

// Render reports as beautiful cards
function renderReports(filter = '') {
  const container = document.getElementById('reportsList');
  const lowerFilter = filter.toLowerCase();

  const filtered = reports.filter(r => 
    !lowerFilter || 
    r.username.toLowerCase().includes(lowerFilter) ||
    r.reason.toLowerCase().includes(lowerFilter) ||
    r.details.toLowerCase().includes(lowerFilter)
  );

  if (filtered.length === 0) {
    container.innerHTML = `<p class="text-center text-gray-500 py-12">No reports found matching "${filter}"</p>`;
    return;
  }

  container.innerHTML = filtered.map(r => {
    const date = new Date(r.timestamp).toLocaleString('en-US', { 
      month: 'short', day: 'numeric', hour: 'numeric', minute: '2-digit' 
    });
    const reasonColor = {
      harassment: 'bg-red-100 text-red-700',
      spam: 'bg-orange-100 text-orange-700',
      cheating: 'bg-purple-100 text-purple-700',
      inappropriate: 'bg-pink-100 text-pink-700',
      threats: 'bg-red-100 text-red-700',
      other: 'bg-gray-100 text-gray-700'
    }[r.reason] || 'bg-gray-100 text-gray-700';

    return `
      <div class="bg-white p-6 rounded-3xl shadow-sm border border-gray-100 hover:shadow-md transition">
        <div class="flex justify-between items-start mb-3">
          <div>
            <span class="font-semibold text-lg">${r.anonymous ? 'Anonymous' : r.username}</span>
            <span class="ml-3 text-xs px-3 py-1 rounded-full ${reasonColor}">${r.reason}</span>
          </div>
          <span class="text-xs text-gray-500">${date}</span>
        </div>
        
        <p class="text-gray-700 leading-relaxed mb-4">${r.details}</p>
        
        ${r.evidence.length ? `
        <div class="mb-4">
          <span class="text-xs uppercase tracking-widest text-gray-500">Evidence:</span>
          <div class="flex flex-wrap gap-2 mt-1">
            ${r.evidence.map(file => `<span class="text-xs bg-gray-100 px-3 py-1 rounded-xl">${file}</span>`).join('')}
          </div>
        </div>` : ''}
        
        <button onclick="deleteReport('${r.id}')" 
          class="text-red-500 hover:text-red-700 text-sm font-medium flex items-center gap-1">
          🗑️ Delete report
        </button>
      </div>
    `;
  }).join('');
}

// Delete single report
window.deleteReport = function(id) {
  if (confirm('Delete this report?')) {
    reports = reports.filter(r => r.id !== id);
    localStorage.setItem('kylitoReports', JSON.stringify(reports));
    renderReports(document.getElementById('searchInput').value);
  }
};

// Clear everything (demo only)
window.clearAllReports = function() {
  if (confirm('Clear ALL reports? This cannot be undone.')) {
    reports = [];
    localStorage.setItem('kylitoReports', JSON.stringify(reports));
    renderReports(document.getElementById('searchInput').value);
  }
};

// Tab switching
function showSubmit() {
  document.getElementById('submitSection').classList.remove('hidden');
  document.getElementById('viewSection').classList.add('hidden');
  document.getElementById('submitTab').classList.add('border-blue-600', 'text-blue-600');
  document.getElementById('submitTab').classList.remove('text-gray-500');
  document.getElementById('viewTab').classList.remove('border-blue-600', 'text-blue-600');
  document.getElementById('viewTab').classList.add('text-gray-500');
}

function showView() {
  document.getElementById('submitSection').classList.add('hidden');
  document.getElementById('viewSection').classList.remove('hidden');
  document.getElementById('submitTab').classList.remove('border-blue-600', 'text-blue-600');
  document.getElementById('submitTab').classList.add('text-gray-500');
  document.getElementById('viewTab').classList.add('border-blue-600', 'text-blue-600');
  renderReports(document.getElementById('searchInput').value);
}

// Form handling + file preview
document.getElementById('reportForm').addEventListener('submit', function(e) {
  e.preventDefault();

  const formData = new FormData(e.target);
  const evidenceFiles = Array.from(document.getElementById('evidence').files).map(f => f.name);

  const newReport = {
    id: Date.now().toString(),
    username: formData.get('username'),
    reason: formData.get('reason'),
    details: formData.get('details'),
    anonymous: formData.get('anonymous') === 'on',
    evidence: evidenceFiles,
    timestamp: new Date().toISOString()
  };

  reports.unshift(newReport);
  localStorage.setItem('kylitoReports', JSON.stringify(reports));

  // Show success
  document.getElementById('successMessage').classList.remove('hidden');
  document.getElementById('errorMessage').classList.add('hidden');

  // Clear form
  e.target.reset();
  document.getElementById('previewContainer').innerHTML = '';

  // Auto-switch to View Reports after 1.5 seconds
  setTimeout(() => {
    showView();
    document.getElementById('successMessage').classList.add('hidden');
  }, 1500);
});

// File preview (filenames)
document.getElementById('evidence').addEventListener('change', function() {
  const container = document.getElementById('previewContainer');
  container.innerHTML = '';
  Array.from(this.files).forEach(file => {
    const div = document.createElement('div');
    div.className = 'text-xs bg-gray-100 px-4 py-2 rounded-2xl';
    div.textContent = file.name;
    container.appendChild(div);
  });
});

// Search (real-time)
document.getElementById('searchInput').addEventListener('input', (e) => {
  renderReports(e.target.value);
});

// Initialize everything
window.onload = function() {
  initReports();
  showSubmit();   // start on submit tab
};
const slides = document.querySelectorAll('.slide');
const slider = document.querySelector('.slider');
let index = 0;

document.querySelector('.next').onclick = () => show(index + 1);
document.querySelector('.prev').onclick = () => show(index - 1);

function show(i) {
  index = (i + slides.length) % slides.length;
  slider.style.transform = `translateX(-${index * 100}%)`;
}

const commonOpt = {
  responsive: true,
  animation: { duration: 1200 },
  plugins: {
    legend: { labels: { color: '#fff' } }
  },
  scales: {
    x: { ticks: { color: '#fff' } },
    y: { ticks: { color: '#fff' } }
  }
};

// Chart 2 Example
new Chart(document.getElementById('chart2'), {
  type: 'bar',
  data: {
    labels: ['Docs', 'Models', 'Practice', 'Eval'],
    datasets: [{
      data: [20, 40, 60, 80],
      backgroundColor: ['#004990', '#3377cc', '#66a3ff', '#99c2ff']
    }]
  },
  options: commonOpt
});

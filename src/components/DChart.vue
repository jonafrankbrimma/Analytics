<script>
import { Doughnut } from 'vue-chartjs'

export default {
  extends: Doughnut,
  mounted () {
    this.renderChart({
      labels: ['Vivian Brian', 'Laura Gilligan', 'Allen Gill', 'Michael Clarkson'],
      datasets: [
        {
          backgroundColor: [
            '#41B883',
            '#E46651',
            '#00D8FF',
            '#DD1B16'
          ],
          data: [40, 20, 80, 10]
        }
      ]
    },
    { responsive: true, maintainAspectRatio: false })
  }
}
</script>

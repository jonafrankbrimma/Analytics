<script>
import { Line } from 'vue-chartjs'

export default {
  extends: Line,
  mounted () {
    this.renderChart({
      labels: ['Processing', 'Submittal', 'Cond.Approval', 'Resubmittal', 'Approval', 'Docs Out'],
      datasets: [
        {
          label: 'Count',
          backgroundColor: '#f87979',
          data: [40, 39, 10, 40, 39, 80]
        }
      ]
    }, { responsive: true, maintainAspectRatio: false })
  }
}
</script>

# UnityCodes Activate Animation NPCTrigger.

using UnityEngine;

public class NPCAnimationTrigger : MonoBehaviour
{
    public Animator npcAnimator; // Asigna el Animator del NPC en el Inspector
    public string animationTriggerName = "Wave"; // Nombre del Trigger en el Animator

    private void Start()
    {
        if (npcAnimator == null)
        {
            Debug.LogError("❌ No se encontró el Animator del NPC. Asigna el Animator en el Inspector.");
        }
    }

    private void OnTriggerEnter(Collider other)
    {
        if (other.CompareTag("Player") && npcAnimator != null)
        {
            Debug.Log("👋 Player detectado, activando animación del NPC");
            npcAnimator.SetTrigger(animationTriggerName); // Activa la animación
        }
    }
}

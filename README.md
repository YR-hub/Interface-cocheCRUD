public interface CocheCRUD {
    void save(Coche coche);
    List<Coche> findAll();
    void delete(Coche coche);
}

  public class CocheCRUDImpl implements CocheCRUD {
    private List<Coche> coches = new ArrayList<>();

    @Override
    public void save(Coche coche) {
        coches.add(coche);
        System.out.println("Coche guardado: " + coche.toString());
    }

    @Override
    public List<Coche> findAll() {
        System.out.println("Encontrados todos los coches");
        return coches;
    }

    @Override
    public void delete(Coche coche) {
        coches.remove(coche);
        System.out.println("Coche eliminado: " + coche.toString());
    }
}
public class Main {
    public static void main(String[] args) {
        CocheCRUD cocheCrud = new CocheCRUDImpl();
        cocheCrud.save(new Coche("Audi", "A4", 2020));
        cocheCrud.findAll();
        cocheCrud.delete(new Coche("Audi", "A4", 2020));
    }
}
